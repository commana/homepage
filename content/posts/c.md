---
title: "C"
date: 2020-05-12T19:10:49+02:00
draft: false
categories:
- digital garden
tags:
- basics
- c
- programming
---

The C programming language can be difficult for developers that are used to high-level concepts and libraries from their favorite language. At least for me, going "back" to C from languages like Java or JavaScript feels daunting. 

Since I decided to write programs in the spirit of [Donald Knuth]({{< relref "programs.md" >}}), I took on two projects that I am going to write in C: an image viewer with programming language support -- where the programming language will be the second project. I'm going to combine both ideas/projects at some later point. For now, I'll just develop them side by side.

Although I learned C during my first semester at University, my memory has almost faded. So I'm practically starting from scratch. I take this as an opportunity to refresh my knowledge and this post will contain all the little snippets that I will find useful to remember.

As always in my [Digital Garden]({{< relref "/about/index.md" >}}), I'm going to update this post from time to time.

-------

**Note:** These examples reflect my current understanding of programming in C. They're almost certainly not the most easiest, most efficient, or otherwise most optimized versions of the specific tasks they try to achieve. So, be warned. :-)

### Dynamic two-dimensional char array

This is a simplified version of how to create a dynamically-sized, two-dimensional char array. 

```C
// Initialize 2-dimensional char array,
// i.e. an array of strings.
int num_entries = 42; // this would be dynamic
char **array_of_strings = malloc(num_entries * sizeof(char*));

// .. now for every entry we need to create space
// Imagine we are looping through 'num_entries' using 'index':
int index = 21; // would be a loop counter
int len = 10; // The length of the string we want to store.
              // If this would be derived from strlen,
              // we would need to add 1 to incorporate '\0'.
array_of_strings[index] = malloc(len * sizeof(char));

// ... ready to go:
strcpy(array_of_strings[index], "a string");
// or whatever we want to do ...

// And don't forget to free all pointers
// by looping through 'num_entries':
free(array_of_strings[index]); // free each string
free(array_of_strings); // free the array itself
```

-------

(To be continued.)

