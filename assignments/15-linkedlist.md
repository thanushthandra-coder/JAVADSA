1. Singly Linked List

program:
class Main {

    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    public static void main(String[] args) {

        Node head = new Node(10);
        head.next = new Node(20);
        head.next.next = new Node(30);

        Node temp = head;

        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
    }
}

output:

10 20 30

Structure:

10 → 20 → 30 → NULL

2. Doubly Linked List

program:
class Main {

    static class Node {
        int data;
        Node prev;
        Node next;

        Node(int data) {
            this.data = data;
            this.prev = null;
            this.next = null;
        }
    }

    public static void main(String[] args) {

        Node first = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);

        first.next = second;

        second.prev = first;
        second.next = third;

        third.prev = second;

        Node temp = first;

        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
    }
}

output:

10 20 30

Structure:

NULL ← 10 ⇄ 20 ⇄ 30 → NULL

3. Circular Linked List

program:
class Main {

    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    public static void main(String[] args) {

        Node first = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);

        first.next = second;
        second.next = third;

        // Last node points back to first
        third.next = first;

        Node temp = first;

        do {
            System.out.print(temp.data + " ");
            temp = temp.next;
        } while (temp != first);
    }
}

output:

10 20 30

Structure:

10 → 20 → 30 → 10 → ...



#Easy

1. Convert Binary Number in a Linked List to Integer
  
program:
public class Main {

    // Node of the linked list
    static class ListNode {
        int val;
        ListNode next;

        ListNode(int val) {
            this.val = val;
        }
    }

    // Convert binary linked list to integer
    public static int getDecimalValue(ListNode head) {
        int result = 0;

        while (head != null) {
            result = result * 2 + head.val;
            head = head.next;
        }

        return result;
    }

    public static void main(String[] args) {

        // Create linked list: 1 -> 0 -> 1 -> 1
        ListNode head = new ListNode(1);
        head.next = new ListNode(0);
        head.next.next = new ListNode(1);
        head.next.next.next = new ListNode(1);

        // Convert binary to decimal
        int answer = getDecimalValue(head);

        System.out.println("Decimal value: " + answer);
    }
}

output:

Decimal value: 11

2. Reverse Linked List

program:
public class Main {

    // Node class
    static class ListNode {
        int val;
        ListNode next;

        ListNode(int val) {
            this.val = val;
        }
    }

    // Function to reverse the linked list
    public static ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode current = head;

        while (current != null) {
            ListNode next = current.next; // Save next node
            current.next = prev;          // Reverse the link
            prev = current;               // Move prev forward
            current = next;               // Move current forward
        }

        return prev;
    }

    // Print linked list
    public static void printList(ListNode head) {
        while (head != null) {
            System.out.print(head.val);

            if (head.next != null) {
                System.out.print(" -> ");
            }

            head = head.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {

        // Create linked list: 1 -> 2 -> 3 -> 4 -> 5
        ListNode head = new ListNode(1);
        head.next = new ListNode(2);
        head.next.next = new ListNode(3);
        head.next.next.next = new ListNode(4);
        head.next.next.next.next = new ListNode(5);

        System.out.println("Original list:");
        printList(head);

        // Reverse the list
        head = reverseList(head);

        System.out.println("Reversed list:");
        printList(head);
    }
}

output:

Original list:
1 -> 2 -> 3 -> 4 -> 5

Reversed list:
5 -> 4 -> 3 -> 2 -> 1

3. Middle of the Linked List

program:
public class Main {

    // Node class
    static class ListNode {
        int val;
        ListNode next;

        ListNode(int val) {
            this.val = val;
        }
    }

    // Find the middle node
    public static ListNode middleNode(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;

        // slow moves 1 step, fast moves 2 steps
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }

        return slow;
    }

    public static void main(String[] args) {

        // Create linked list:
        // 1 -> 2 -> 3 -> 4 -> 5
        ListNode head = new ListNode(1);
        head.next = new ListNode(2);
        head.next.next = new ListNode(3);
        head.next.next.next = new ListNode(4);
        head.next.next.next.next = new ListNode(5);

        // Find middle
        ListNode middle = middleNode(head);

        System.out.println("Middle node: " + middle.val);
    }
}

output:

Middle node: 3

#Mediam:

1. Design Twitter

program:
import java.util.*;

public class Main {

    static class Twitter {

        // Store tweets for each user
        Map<Integer, List<Tweet>> tweets;

        // Store who each user follows
        Map<Integer, Set<Integer>> following;

        int time = 0;

        // Tweet class
        class Tweet {
            int tweetId;
            int time;

            Tweet(int tweetId, int time) {
                this.tweetId = tweetId;
                this.time = time;
            }
        }

        public Twitter() {
            tweets = new HashMap<>();
            following = new HashMap<>();
        }

        // Post a tweet
        public void postTweet(int userId, int tweetId) {
            tweets.putIfAbsent(userId, new ArrayList<>());

            tweets.get(userId).add(new Tweet(tweetId, time++));
        }

        // Get the 10 most recent tweets
        public List<Integer> getNewsFeed(int userId) {

            List<Tweet> allTweets = new ArrayList<>();

            // Add user's own tweets
            if (tweets.containsKey(userId)) {
                allTweets.addAll(tweets.get(userId));
            }

            // Add tweets from people user follows
            if (following.containsKey(userId)) {
                for (int person : following.get(userId)) {
                    if (tweets.containsKey(person)) {
                        allTweets.addAll(tweets.get(person));
                    }
                }
            }

            // Sort newest first
            allTweets.sort((a, b) -> b.time - a.time);

            List<Integer> result = new ArrayList<>();

            // Return at most 10 tweets
            for (int i = 0; i < Math.min(10, allTweets.size()); i++) {
                result.add(allTweets.get(i).tweetId);
            }

            return result;
        }

        // Follow another user
        public void follow(int followerId, int followeeId) {
            following.putIfAbsent(followerId, new HashSet<>());

            following.get(followerId).add(followeeId);
        }

        // Unfollow a user
        public void unfollow(int followerId, int followeeId) {
            if (following.containsKey(followerId)) {
                following.get(followerId).remove(followeeId);
            }
        }
    }

    public static void main(String[] args) {

        Twitter twitter = new Twitter();

        // User 1 posts tweet 101
        twitter.postTweet(1, 101);

        // User 1 follows user 2
        twitter.follow(1, 2);

        // User 2 posts tweet 102
        twitter.postTweet(2, 102);

        // Get user 1's news feed
        System.out.println(twitter.getNewsFeed(1));

        // User 1 unfollows user 2
        twitter.unfollow(1, 2);

        // Get news feed again
        System.out.println(twitter.getNewsFeed(1));
    }
}

output:

[102, 101]
[101]

2. Design Linked List

program:
public class Main {

    static class MyLinkedList {

        // Node class
        class Node {
            int val;
            Node next;

            Node(int val) {
                this.val = val;
                this.next = null;
            }
        }

        Node head;
        int size;

        // Constructor
        public MyLinkedList() {
            head = null;
            size = 0;
        }

        // Get value at index
        public int get(int index) {

            if (index < 0 || index >= size) {
                return -1;
            }

            Node current = head;

            for (int i = 0; i < index; i++) {
                current = current.next;
            }

            return current.val;
        }

        // Add node at the beginning
        public void addAtHead(int val) {

            Node newNode = new Node(val);

            newNode.next = head;
            head = newNode;

            size++;
        }

        // Add node at the end
        public void addAtTail(int val) {

            Node newNode = new Node(val);

            if (head == null) {
                head = newNode;
            } else {

                Node current = head;

                while (current.next != null) {
                    current = current.next;
                }

                current.next = newNode;
            }

            size++;
        }

        // Add node at a specific index
        public void addAtIndex(int index, int val) {

            if (index < 0 || index > size) {
                return;
            }

            // Add at beginning
            if (index == 0) {
                addAtHead(val);
                return;
            }

            // Add at end
            if (index == size) {
                addAtTail(val);
                return;
            }

            Node newNode = new Node(val);
            Node current = head;

            // Move to node before index
            for (int i = 0; i < index - 1; i++) {
                current = current.next;
            }

            newNode.next = current.next;
            current.next = newNode;

            size++;
        }

        // Delete node at index
        public void deleteAtIndex(int index) {

            if (index < 0 || index >= size) {
                return;
            }

            // Delete head
            if (index == 0) {
                head = head.next;
                size--;
                return;
            }

            Node current = head;

            // Move to node before index
            for (int i = 0; i < index - 1; i++) {
                current = current.next;
            }

            current.next = current.next.next;

            size--;
        }

        // Print linked list
        public void printList() {

            Node current = head;

            while (current != null) {
                System.out.print(current.val);

                if (current.next != null) {
                    System.out.print(" -> ");
                }

                current = current.next;
            }

            System.out.println();
        }
    }

    public static void main(String[] args) {

        MyLinkedList list = new MyLinkedList();

        // Add at head
        list.addAtHead(1);

        // Add at tail
        list.addAtTail(3);

        // Add 2 at index 1
        list.addAtIndex(1, 2);

        System.out.println("Linked List:");
        list.printList();

        // Get value
        System.out.println("Value at index 1: " + list.get(1));

        // Delete index 1
        list.deleteAtIndex(1);

        System.out.println("After deleting index 1:");
        list.printList();
    }
}

output:

Linked List:
1 -> 2 -> 3
Value at index 1: 2
After deleting index 1:
1 -> 3

3. Reverse Linked List II

program:
public class Main {

    static class ListNode {
        int val;
        ListNode next;

        ListNode(int val) {
            this.val = val;
        }
    }

    public static ListNode reverseBetween(ListNode head, int left, int right) {

        // Dummy node helps when left = 1
        ListNode dummy = new ListNode(0);
        dummy.next = head;

        ListNode prev = dummy;

        // Move prev to the node before 'left'
        for (int i = 1; i < left; i++) {
            prev = prev.next;
        }

        // Reverse the required portion
        ListNode current = prev.next;

        for (int i = 0; i < right - left; i++) {

            ListNode next = current.next;

            current.next = next.next;
            next.next = prev.next;
            prev.next = next;
        }

        return dummy.next;
    }

    // Print linked list
    public static void printList(ListNode head) {

        while (head != null) {
            System.out.print(head.val);

            if (head.next != null) {
                System.out.print(" -> ");
            }

            head = head.next;
        }

        System.out.println();
    }

    public static void main(String[] args) {

        // Create:
        // 1 -> 2 -> 3 -> 4 -> 5
        ListNode head = new ListNode(1);
        head.next = new ListNode(2);
        head.next.next = new ListNode(3);
        head.next.next.next = new ListNode(4);
        head.next.next.next.next = new ListNode(5);

        System.out.println("Original list:");
        printList(head);

        // Reverse positions 2 to 4
        head = reverseBetween(head, 2, 4);

        System.out.println("After reversing:");
        printList(head);
    }
}

output:

Original list:
1 -> 2 -> 3 -> 4 -> 5

After reversing:
1 -> 4 -> 3 -> 2 -> 5

#Hard

1. Reverse Nodes in k-Group

program:
public class Main {

    static class ListNode {
        int val;
        ListNode next;

        ListNode(int val) {
            this.val = val;
        }
    }

    public static ListNode reverseKGroup(ListNode head, int k) {

        if (head == null || k == 1) {
            return head;
        }

        ListNode dummy = new ListNode(0);
        dummy.next = head;

        ListNode groupPrev = dummy;

        while (true) {

            // Find the kth node
            ListNode kth = getKthNode(groupPrev, k);

            // If fewer than k nodes remain, don't reverse
            if (kth == null) {
                break;
            }

            ListNode groupNext = kth.next;

            // Reverse the group
            ListNode prev = groupNext;
            ListNode current = groupPrev.next;

            while (current != groupNext) {
                ListNode next = current.next;
                current.next = prev;
                prev = current;
                current = next;
            }

            // Connect previous part to reversed group
            ListNode temp = groupPrev.next;
            groupPrev.next = kth;

            // Move groupPrev to the end of reversed group
            groupPrev = temp;
        }

        return dummy.next;
    }

    // Find kth node from groupPrev
    public static ListNode getKthNode(ListNode groupPrev, int k) {

        ListNode current = groupPrev;

        for (int i = 0; i < k; i++) {
            current = current.next;

            if (current == null) {
                return null;
            }
        }

        return current;
    }

    // Print linked list
    public static void printList(ListNode head) {

        while (head != null) {
            System.out.print(head.val);

            if (head.next != null) {
                System.out.print(" -> ");
            }

            head = head.next;
        }

        System.out.println();
    }

    public static void main(String[] args) {

        // Create:
        // 1 -> 2 -> 3 -> 4 -> 5
        ListNode head = new ListNode(1);
        head.next = new ListNode(2);
        head.next.next = new ListNode(3);
        head.next.next.next = new ListNode(4);
        head.next.next.next.next = new ListNode(5);

        int k = 2;

        System.out.println("Original list:");
        printList(head);

        head = reverseKGroup(head, k);

        System.out.println("After reversing in groups of " + k + ":");
        printList(head);
    }
}

output:

Original list:
1 -> 2 -> 3 -> 4 -> 5
After reversing in groups of 2:
2 -> 1 -> 4 -> 3 -> 5

2. LFU Cache

program:
import java.util.*;

public class Main {

    static class LFUCache {

        int capacity;
        int minFreq;

        // key -> Node
        HashMap<Integer, Node> keyMap;

        // frequency -> LinkedHashSet of keys
        HashMap<Integer, LinkedHashSet<Integer>> freqMap;

        static class Node {
            int key;
            int value;
            int freq;

            Node(int key, int value) {
                this.key = key;
                this.value = value;
                this.freq = 1;
            }
        }

        public LFUCache(int capacity) {
            this.capacity = capacity;
            this.minFreq = 0;

            keyMap = new HashMap<>();
            freqMap = new HashMap<>();
        }

        // Get value
        public int get(int key) {

            if (!keyMap.containsKey(key)) {
                return -1;
            }

            Node node = keyMap.get(key);

            // Increase frequency
            increaseFrequency(node);

            return node.value;
        }

        // Put key and value
        public void put(int key, int value) {

            if (capacity == 0) {
                return;
            }

            // If key already exists
            if (keyMap.containsKey(key)) {

                Node node = keyMap.get(key);

                node.value = value;

                increaseFrequency(node);

                return;
            }

            // Cache is full
            if (keyMap.size() >= capacity) {

                // Get keys with minimum frequency
                LinkedHashSet<Integer> keys = freqMap.get(minFreq);

                // Remove the least recently used key
                int removeKey = keys.iterator().next();

                keys.remove(removeKey);
                keyMap.remove(removeKey);

                if (keys.isEmpty()) {
                    freqMap.remove(minFreq);
                }
            }

            // Add new node
            Node newNode = new Node(key, value);

            keyMap.put(key, newNode);

            freqMap.putIfAbsent(1, new LinkedHashSet<>());
            freqMap.get(1).add(key);

            minFreq = 1;
        }

        // Increase frequency of a node
        private void increaseFrequency(Node node) {

            int oldFreq = node.freq;

            LinkedHashSet<Integer> oldSet = freqMap.get(oldFreq);

            oldSet.remove(node.key);

            if (oldSet.isEmpty()) {

                freqMap.remove(oldFreq);

                // If this was the minimum frequency
                if (minFreq == oldFreq) {
                    minFreq++;
                }
            }

            // Increase frequency
            node.freq++;

            freqMap.putIfAbsent(node.freq, new LinkedHashSet<>());
            freqMap.get(node.freq).add(node.key);
        }
    }

    public static void main(String[] args) {

        LFUCache cache = new LFUCache(2);

        cache.put(1, 10);
        cache.put(2, 20);

        System.out.println(cache.get(1));

        cache.put(3, 30);

        System.out.println(cache.get(2));
        System.out.println(cache.get(3));

        cache.put(4, 40);

        System.out.println(cache.get(1));
        System.out.println(cache.get(3));
        System.out.println(cache.get(4));
    }
}

output:

10
-1
30
-1
30
40

3. Merge k Sorted Lists

program:

import java.util.PriorityQueue;

public class Main {

    static class ListNode {
        int val;
        ListNode next;

        ListNode(int val) {
            this.val = val;
        }
    }

    public static ListNode mergeKLists(ListNode[] lists) {

        // Min Heap
        PriorityQueue<ListNode> pq =
            new PriorityQueue<>((a, b) -> a.val - b.val);

        // Add first node of every list
        for (ListNode list : lists) {
            if (list != null) {
                pq.offer(list);
            }
        }

        // Dummy node
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;

        while (!pq.isEmpty()) {

            // Get smallest node
            ListNode smallest = pq.poll();

            // Add it to result
            current.next = smallest;
            current = current.next;

            // Add next node from same list
            if (smallest.next != null) {
                pq.offer(smallest.next);
            }
        }

        return dummy.next;
    }

    // Print linked list
    public static void printList(ListNode head) {

        while (head != null) {
            System.out.print(head.val);

            if (head.next != null) {
                System.out.print(" -> ");
            }

            head = head.next;
        }

        System.out.println();
    }

    public static void main(String[] args) {

        // List 1: 1 -> 4 -> 5
        ListNode list1 = new ListNode(1);
        list1.next = new ListNode(4);
        list1.next.next = new ListNode(5);

        // List 2: 1 -> 3 -> 4
        ListNode list2 = new ListNode(1);
        list2.next = new ListNode(3);
        list2.next.next = new ListNode(4);

        // List 3: 2 -> 6
        ListNode list3 = new ListNode(2);
        list3.next = new ListNode(6);

        // Store all lists
        ListNode[] lists = {list1, list2, list3};

        // Merge
        ListNode result = mergeKLists(lists);

        System.out.println("Merged list:");
        printList(result);
    }
}

output:

Merged list:
1 -> 1 -> 2 -> 3 -> 4 -> 4 -> 5 -> 6
