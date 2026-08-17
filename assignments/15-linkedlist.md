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
