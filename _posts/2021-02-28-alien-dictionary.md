---
layout: post
title: Alien Dictionary
excerpt: Graph, DFS, Adjacency List
---
 

## Solution

I refactored the solution that I found online.

```ruby
def alien_order(words)        
  graph = Graph.new
    
  # Add nodes to the graph. No neighbors added at this time.
  words.each do |word|
    word.each_char do |c|
      graph.add_node(c)
    end
  end
    
  # Create graph
  (words.size - 1).times do |i|
    # ['abc', 'ab'] is not valid, return ''
    if words[i].size != words[i+1].size
      if words[i].start_with?(words[i+1])
        return ''
      end
    end
    
    # Create the precedence rules
    words[i].each_char.with_index do |c, j|
      if words[i+1][j] && c != words[i+1][j]
        graph.add_edge(c, words[i+1][j])
        
        break
      end
    end
  end
    
  # DFS Toplogical Sort
  TopSort.new(graph).sort
end

class TopSort
  def initialize(graph)
    @adj = graph.adj
    @stack = []
    @visited = {}
  end
    
  def sort
    @adj.keys.each do |node|
      return '' if @visited[node].nil? && dfs(node)
    end
        
    @stack.join('')
  end
    
  def dfs(node)
    @visited[node] = false
        
    @adj[node].each do |neighbor|
      # We can explore neighbors only if it has not been explored  
      if @visited[neighbor].nil?
        # Explore only if the neighbor has neighbors to be explored
        if @adj[neighbor]
          return true if dfs(neighbor)
        end        
      else
        return true if !@visited[neighbor]
      end 
    end

    # adds the node to the beginning of the array
    # this happens when recursive calls begin to return
    @stack.unshift(node)
    @visited[node] = true
        
    false
  end
end

class Graph
  attr_accessor :adj
    
  def initialize
    @adj = Hash.new([])
  end
    
  def add_node(node)
    @adj[node] = []
  end
    
  def add_edge(source, dest)
    # Nothing to do, if the precedence rule is already defined
    return if @adj[source].include?(dest)
        
    @adj[source].push(dest)
  end
end

```

Few more lines to be cleaned up in the dfs method.

