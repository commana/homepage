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

?? Linked lists in Haskell, Scheme, and maybe even C.
==> use head/tail idea for linked lists (haskell notation)

Talk about repl.it: How to run junit?

- insert: O(1) ==> insert at the front
- find: O(n) ==> find the first entry that matches and return it as the head of a smaller linked list
- delete: O(n) ==> delete element and reconnect elements to fill the gap
- what test cases are important for each operation?

How I tried to implement them ... and failed. I lost control of how the list could be used (clients had "pointers" to elements that should have been deleted)

How embracing the language (Java) and with it OO concepts (specifically encapsulation) saved my day.
