---
layout: post
title: I think I'm in love with LRU
link: http://tech.dropbox.com/2012/10/caching-in-theory-and-practice/
---

Dropbox's [engineering blog][] details the theory and rational behind the caching algorithm that they've chosen for their mobile client. It's a very insightful read that compares between Most Recently Used (MRU), Least Recently Used (LRU) and Least Frequently Used (LFU). 

Here's my implementation of LRU caching in Java:

    public class LRUCache<K, T> {

      class Node {
        Node prev;
        Node next;
        K key;
        T data;
        public Node(K key, T data) {
          this.key = key;
          this.data = data;
        }
      }
      
      HashMap<K, Node> map;
      Node head;
      Node tail;
      int maxSize;
      
      public LRUCache(int maxSize) {
        this.maxSize = maxSize;
        head = new Node(null, null);
        tail = new Node(null, null);
        head.next = tail;
        tail.prev = head;
      }
      
      private void detach(Node node) {
        node.prev.next = node.next;
        node.next.prev = node.prev;
      }
      
      private void attach(Node head, Node node) {
        node.prev = head;
        node.next = head.next;
        node.next.prev = node;
        node.prev.next = node;
      }
      
      public T get(K key) {
        Node node = map.get(key);
        if (node == null)
          return null;
        if (map.size() == 1)
          return node.data;
        detach(head);
        attach(head, node);
        return node.data;
      }
      
      public void put(K key, T data) {
        if (maxSize <= 0)
          return;
        Node node = map.get(key);
        if (node != null) {
          // hit, refresh the data
          detach(node);
          attach(head, node);
          node.data = data;
        } else {
          // miss, create new node and adjust the size
          node = new Node(key, data);
          map.put(key, node);
          attach(head, node);
          if (map.size() > maxSize) {
            detach(tail.prev);
            map.remove(tail.prev.key);
          }
        }
      }
    }

[engineering blog]: http://tech.dropbox.com/2012/10/caching-in-theory-and-practice/ "Dropbox Engineering Blog"