---
title: "Linked Lists"
date: 2020-04-15T17:46:52+02:00
draft: true
categories:
- digital garden
tags:
- data structures
- basics
- java
---

A lesson in object orientation and Java

What are linked lists? They are a very basic data structure that can be used to store a (theoretically) unbounded number of elements without having to allocate the required space upfront like an array. While an array has O(1) random access, i.e. every element in an array can be accessed in constant time, a linked list does not have this feature. Instead, the list has to be traversed sequentially (typically using a `next` pointer) to reach a specific element, resulting in O(n) access time.

A useful linked list supports three operations:

- insert: O(1) ==> insert at the front
- find: O(n) ==> find the first entry that matches (and provide it as the head of a smaller linked list)
- delete: O(n) ==> delete element and reconnect elements to fill the gap
- what test cases are important for each operation?

So as a really simple exercise I wanted to implement such a linked list in Java (ok, I know, it's 2020...). This should be fairly simple, right?

As it turned out, I failed! My problem weren't the operations, but how I handled encapsulation. My raw linked list entry was accessible to the client, which could do whatever it wanted with it. Specifically, it got hold of a reference to certain elements. This means that we now lost control over our data structure once we want to manipulate it. This wouldn't be a problem with an immutable implementation, but I decided that it should be a mutable linked list, as this felt most natural in Java.

Here is a quick glance on the interface of my first attempt in Java:

```java
class LinkedList<T> {
  public T item;
  public LinkedList<T> next;

  public boolean isEmpty() { ... }

  public LinkedList<T> find(T item) { ... }

  public LinkedList<T> insert(T item) { ... }

  public void delete(T item) { ... }
}
```

My problem was with the `insert` operation: How do you insert a new element in front while the client still has a reference to the current first element? My solution was to return a new list, which the client should then use. This exposes more references. Now, the `delete` operation I implemented suddenly wants a mutable linked list (signaled by the `void` return type). Conflict of interest! So we are actually mixing mutable and immutable operations together. No wonder this does not work.

## Mistake #1: No concept of a list head

Linked list implementations in other languages often only allow access to values through a "head" and a "tail" (also called "rest") function:

```haskell
> head [1,2,3]
1
> tail [1,2,3]
[2,3]
```

So, how does this help me in implementing a linked list in Java? Accessing an element should only be possible through the `head` function. It exposes the value we contain in a linked list element, but nothing else. `head` and `tail` expose the recursive nature of a linked list, so that the list could be iterated by a combination of calls to `head` and `tail`. As such, it makes sense to have these operations in my own implementation.

## Mistake #2: Not embracing the language

I tried to implement it like in C: having a "pure" data structure (a C-based `struct`) and additionally some procedures, which would operate on the data structure. Since we are working on a mutable version of a list, we should encapsulate everything so that only the key operations are exposed. Everything else should be hidden from the client.

Java is call by value, so references to objects cannot be changed. This is different compared to C, where pointers can be manipulated. Since I did not have a dedicated list head, clients needed to maintained their own head of the list. After insertion, they would need to update the head themselves.
Since they could keep the previous `head` references in a variable, the deletion of an element was now impossible: since they could still have a reference for the deleted element, it would appear as if that element still existed, even though the element would have been skipped in the "real" list.
I did not use proper encapsulation as I should. In Java, that's what classes are for. We need to maintain our own `head` of the list, and keep the internals of the list private, by allowing access and manipulation of the list only through dedicated public methods. This is similar to the `head` and `tail` functions in my example above, because they also do not expose any implementation details.

## Mistake #3: Allowing direct access to linked list elements

data encapsulation and information hiding.

I declared all my fields `public`. Fat mistake? Not necessarily, I'm the only one using my linked list class. So obviously, I have nothing to hide from myself lol.

## Conclusion

It is worth it to implement basic data structure in your language of choice. I really thought this would be no problem for me, since I've been programming for many many years now. But because I've been writing mostly high-level code, I sort-of lost the ability to write the more basic stuff. Even though I technically knew how things should work, actually getting down to work and implement these things is a whole different story.

In the future, I will continue writing simple data structures and also, possibly, some algorithms. This will ensure that this knowledge stays in my memory for longer periods of time. Hopefully, I will never forget the basics again.
