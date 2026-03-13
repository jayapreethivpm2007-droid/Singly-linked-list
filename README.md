class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert(self, data):
        newnode = Node(data)
        newnode.next = self.head
        self.head = newnode

    def delete(self, key):
        temp = self.head

        if temp != None:
            if temp.data == key:
                self.head = temp.next
                return

        prev = None
        while temp != None and temp.data != key:
            prev = temp
            temp = temp.next

        if temp == None:
            print "Element not found"
            return

        prev.next = temp.next

    def display(self):
        temp = self.head
        while temp != None:
            print temp.data,
            temp = temp.next

l = LinkedList()

l.insert(10)
l.insert(20)
l.insert(30)

print "Before Deletion:"
l.display()

l.delete(20)

print "\nAfter Deletion:"
l.display()

Output:

Before Deletion:
30 20 10

After Deletion:
30 10
