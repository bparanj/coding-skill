---
layout: post
title: Linked List Basics
excerpt: Implement traverse and search in a singly linked list.
---


### Node Class

Define a node class for a singly linked list node. In a singly linked list each node is connected to the following node by a single link. Since next is a key word in Ruby, the code uses link as the name instead of next for the pointer to the next element in the linked list. The value is the data stored in the node. The value can be of any type.

```ruby
class Node
  attr_reader :value
  attr_accessor :link

  def initialize(value, link)
    @value = value
    @link = link
  end
end
```

We need a getter for the value because we need to access the value in the node after creating a node object. The value attribute is immutable. We cannot modify the value once we create the node object. We have getter and setter for the link attribute since we need to set and get links of the node. The link pointers are used to traverse the linked list and modify the link pointers to add and remove nodes in a linked list.

### LinkedList Class

Define a class for linked list with constructor that takes the head of the linked list. The head node is the beginning of the linked list.

```ruby
class LinkedList
  def initialize(head)
    @head = head
  end
end
```

### Traversing a LinkedList

Define the traverse method in the linked list class.

```ruby
require_relative 'node'

class LinkedList
  def initialize(head)
    @head = head
  end
  
  # Iterate Over the List
  def traverse
    current = @head

    while current
      p current.value
      current = current.link
    end
  end
end
```

The traverse method starts from the head of the linked list and traverses all the nodes in the linked list and prints the value of the nodes. 

We can include the files that defines the node can linked list class in the file called traverse.rb.

```ruby
require_relative 'node'
require_relative 'linked_list'

# Create the linked List
last = Node.new(14, nil)
second = Node.new(18, last)
head = Node.new(20, second)

list = LinkedList.new(head)
list.traverse
```

Create an instance of the LinkedList class and invoke the traverse method. We create the linked list that contains the nodes with values: 20, 18 and 14. The head node has the value 20 and it links to the second node. The second node connects to the last node. The last node has nil value for the next node since it is the last node. 

### Search a Node

Define a find method in the LinkedList class. It takes the target value of the node to search in the linked list.

```ruby
  # Find a Node
  def find(target)
    current = @head

    while current
      if current.value == target
        return current
      end
      current = current.link
    end  
  end
```

We define a current node that traverses through the linked list and check if the current node value is the same as the target. If so, it returns the node object, otherwise we return nil. We can test this method by invoking the find method on linked list object:

```ruby
node = list.find(18)
p node.value
```

This will print the node value 18.










