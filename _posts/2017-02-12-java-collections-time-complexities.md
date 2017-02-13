---
layout: post
title:  "Java Collections - Time Complexities of each implementation"
date:   2017-02-12
excerpt: "Just about everything about the Java collections api and the time complexities of each implementation"
tag:
- java Collections
- syntax
- big O
- data structures
comments: true
---

## Introduction
The Java platform includes a collections framework. A collection is an object that represents a group of objects (such as the classic Vector class). A collections framework is a unified architecture for representing and manipulating collections, enabling collections to be manipulated independently of implementation details.

The primary advantages of a collections framework are that it:

- **Reduces programming effort** by providing data structures and algorithms so you don't have to write them yourself.
- **Increases performance** by providing high-performance implementations of data structures and algorithms. Because the various implementations of each interface are interchangeable, programs can be tuned by switching implementations.
- **Provides interoperability** between unrelated APIs by establishing a common language to pass collections back and forth.
- **Reduces the effort required to learn APIs** by requiring you to learn multiple ad hoc collection APIs.
- **Reduces the effort required to design and implement APIs** by not requiring you to produce ad hoc collections APIs.
- **Fosters software reuse** by providing a standard interface for collections and algorithms with which to manipulate them.

Following are the time complexities of different data structures and their implementations in the Collections framework.

## List
_A list is an ordered collection of elements._
```java
List<E>
```
Data Structure | Add | Remove | Get | Contains | Based On
-------------- | --- | ------ | --- | -------- | --------
ArrayList |  O(1) | O(n) | O(1) | O(n) | Array
LinkedList | O(1) | O(1) | O(n) | O(n) | Linked List
CopyonWriteArrayList |  O(n) | O(n) | O(1) | O(n) | Array

## Set
_A collection that contains no duplicate elements._
```java
Set<E>
```
Data Structure | Add | Contains | Next | Based On
-------------- | --- | -------- | ---- | --------
HashSet | O(1) | O(1) | O(h/n) | Hash Table
LinkedHashSet | O(1) | O(1) | O(1) | Hash Table + Linked List
EnumSet | O(1) | O(1) | O(1) | Bit Vector
TreeSet | O(log n) | O(log n) | O(log n) | Red-black tree
CopyonWriteArraySet | O(n) | O(n) | O(1) | Array
ConcurrentSkipList | O(log n) | O(log n) | O(1) | Skip List

## Queue
_A collection designed for holding elements prior to processing._
```java
Queue<E>
```
Data Structure| Offer | Peak | Poll | Size | Based On
--------------|-------|------|------|------|---------
PriorityQueue | O(log n ) | O(1) | O(log n) | O(1) | Priority Heap
LinkedList |  O(1) | O(1) | O(1) | O(1) | Array
ArrayDequeue |  O(1) | O(1) | O(1) | O(1) | Linked List
ConcurrentLinkedQueue |  O(1) | O(1) | O(1) | O(n) | Linked List
ArrayBlockingQueue |  O(1) | O(1) | O(1) | O(1) | Array
PriorirityBlockingQueue | O(log n) | O(1) | O(log n) | O(1) | Priority Heap
SynchronousQueue | O(1) | O(1) | O(1) | O(1) | None!
DelayQueue | O(log n) | O(1) | O(log n) | O(1) | Priority Heap
LinkedBlockingQueue | O(1) | O(1) | O(1) | O(1) | Linked List

## Map
_An object that maps keys to values. A map cannot duplicate keys; each key can map to at most one value._
```java
Map<K,V>
```
Data Structure | Get | ContainsKey | Next | Based On
---------------|-----|-------------|------|---------
HashMap | O(1) | O(1) | O(h / n) | Hash Table
LinkedHashMap | O(1) | O(1) | O(1) | Hash Table + Linked List
IdentityHashMap | O(1) | O(1) | O(h / n) | Array
WeakHashMap | O(1) | O(1) | O(h / n) | Hash Table
EnumMap | O(1) | O(1) | O(1) | Array
TreeMap | O(log n) | O(log n) | O(log n) | Red-black tree
ConcurrentHashMap | O(1) | O(1) | O(h / n) | Hash Tables
ConcurrentSkipListMap | O(log n) | O(log n) | O(1) | Skip List

### References:
>[Collections Overview](http://docs.oracle.com/javase/6/docs/technotes/guides/collections/overview.html) has a nice summary table.
>[Annotated Outline](http://docs.oracle.com/javase/6/docs/technotes/guides/collections/reference.html) lists all of the implementations on one page.
