---
layout: post
title: Linked List Basics Part II
excerpt: Implement find_previous_node, add_at_beginning and add_at_end methods in a singly linked list.
---

### Find Previous Node

The dataset used in creating the linked list is the same as the previous article. Define a `find_previous_node` methodin the `LinkedList` class. It takes the target value as the parameter. The method must return the node before the given target value. If the target value is not found in the linked list it will return `nil`.

```ruby
  def find_previous_node(target)
    current = @head

    while current.link 
      if current.link.value == target
        return current
      end
    
      current = current.link
    end
  end
```

The current pointer is initialized to the head of the linked list. The while loop keeps traversing the linked list as long as the `current.link` is not `nil`. This means we stop searching after the last node. Because the last node points to `nil`. The comparison check if the next node value is the same as the target, if it is it returns the current node. Before the start of the next iteration, the current pointer moves to the next node.

```ruby
previous = list.find_previous_node(18)
p previous.value
```

This will print the value of the previous node which is 20. However, this implementation of the `find_previous_node` will crash if the target value is the value of the first node. Because we do not have any node before the first node. This can be demonstrated by running the code:

```ruby
previous = list.find_previous_node(20)
p previous.value
```

### Sentinel Node

The code can be simplified and made crash proof by using a sentinel node. The code for creating the linked list can be modified to include a dummy node to the beginning of the linked list.

```ruby
# Create the linked List
last = Node.new(14, nil)
second = Node.new(18, last)
head = Node.new(20, second)
sentinel = Node.new(0, head)

list = LinkedList.new(sentinel)
```

The sentinel node has 0 as the value for the node. The next node of the sentinel nodes is the head node. Now the implementation of`find_previous_node`will work without crashing if we pass in the head node value as the target. The sentinel node will be returned as the previous node for the head. The main advantage of sentinel node is that we don't need to check for `nil`simplifying the while loop. 

### Add at the Beginning

Implement the `add_at_beginning`method to the `LinkedList` class. It takes the node to be inserted as the parameter. The implementation of inserting a node to the beginning of the linked list is shown below:

```ruby
  def add_at_beginning(node)
    node.link = @head.link
    @head.link = node
  end
```

The linked list values before inserting the new node and after inserting the node is displayed in the code.

```ruby
last = Node.new(14, nil)
second = Node.new(18, last)
head = Node.new(20, second)
sentinel = Node.new(0, head)

list = LinkedList.new(sentinel)
list.traverse

node = Node.new(25, nil)
list.add_at_beginning(node)
list.traverse
```

The sentinel node makes adding a new node to the beginning easier to implement.

### Add at the End

Implement the `add_at_end` method to the `LinkedList`class. It takes the node to be added to the end of the linked list as the parameter. The implementation for adding a node to the end of the linked list class is shown below:

```ruby
  def add_at_end(node)
    current = @head
  
    while current.link
      current = current.link
    end
  
    current.link = node
    node.link = nil
  end
```

The method can be tested by running:

```ruby
last = Node.new(14, nil)
second = Node.new(18, last)
head = Node.new(20, second)
sentinel = Node.new(0, head)

list = LinkedList.new(sentinel)
list.traverse

node = Node.new(25, nil)
list.add_at_end(node)
list.traverse
```

The new node with value 25 will be added to the end of the linked list.
