---
title: "Programs"
date: 2020-05-09T00:10:56+02:00
draft: false
---

> I write an average of five new programs every week. Poets have to write poems. I have to write computer programs.
> - Donald Knuth

Recently, I realized that I haven't been creating real programs for quite some time. I have been creating lots of throwaway scripts, sure, but nothing that felt like a real program. Something that you could give to another person and they would find it useful.

I've also done some LeetCode exercises to refresh my memory about algorithms and data structures. But these aren't real programs, are they?

To me, a program should be something that is complete in itself and does something useful. It should be limited in its feature set, just like the Unix Philosophy says: "Write programs that do one thing and do it well."

Therefore, inspired by Knuth's quote, I set out to craft new programs. I might not be able to code five programs per week, but I take this as a challenge to learn something new every time.

## Inspirations

Here's a list of ideas for programs I gathered before writing this essay. New ideas will get added in the future. For every idea, there is a high-level estimate of its complexity.

Once I make progress towards these ideas, I will update the sections with more information and possibly a link to a new essay that goes more in-depth.

### Use FTL-SDK to send a video to mixer.com

Since I'm a casual streamer on [mixer.com/Brentarus](https://mixer.com/Brentarus), I decided it would be fun to have a lightweight way of sending a video to my Mixer page. Normally, I stream using OBS, but I thought it would be fun to figure out the most bare-bone way of streaming.

The idea is to use the official FTL-SDK that Mixer provides and which OBS uses. The SDK provides a small example application, so this program will be more about infrastructure (eg. Docker) than probably about writing actual code.

*Estimate: Small*

### PUBG-API Stats CLI

Speaking of streaming, my favorite game for the moment is PUBG on Xbox. As is the norm with modern games, they provide an API that lets players look into details of a given match that has been played.

I would like to display a small summary of the recent matches I played, plus the ability to see the rankings of each match on the CLI.

*Estimate: Small*

### PUBG Console Player Queue

PUBG on Xbox in Europe has the problem that there are very few players online during the day or late at night. Since we usually have no idea how many players are online, maybe we could leverage PUBG's API to see how many games with how many players were playing in the last 15 minutes or so. This should give some sort of estimate of how many players may still be playing at a particular time of day.

*Estimate: Small*

### Imager viewer with code support

Previously, I had an idea about a minimal image viewer that supports manipulation through a lisp-like language. I started this project but lost interest along the way.

I recently came across the [Ronin project](https://100r.co/site/ronin.html) which is quite similar to my idea. This is a clear opportunity to revive my project.

*Estimate: Big*

### Blog editor

Using VSCode for my blog somehow doesn't feel right. It's too overpowered for simple blogging. A funny idea would, therefore, be to write a simple Markdown-based editor that supports my blogging workflow.

*Estimate: Big*

### The Brentarus programming language

If you can write your own editor, maybe you could also write your own programming language. Why not? It's been a long time since I have developed a language. Time to start something new and have fun.

*Estimate: Huge*

### Write Unit Tests for a random OSS project

I like writing unit tests, and I try to write as many as I can for my projects. However, there are projects out there that could also benefit from testing. So my idea would be to find a project I like and try to add some test cases.

I understand not every project wants to have tests, or tests just for the sake of them. So we will see if there ever arises an opportunity.

*Estimate: Small*

### "Learning Progress" Microservice

This one has been on my todo list for a while now. For the arsnova.eu project, which is in a phase of transitioning its monolithic Java Spring backend into a microservice architecture, my task would be to extract a specific feature called the "learning progress":

This feature calculates the rate of questions answered correctly by a student and a class, to answer the question: how well is everyone learning?

*Estimate: Medium*

### PUBG CLI Tool to extract clips from a recording

As I said, I like streaming PUBG. For now, I extract interesting clips manually from my recordings. Having the PUBG API (see above), it would be easy to automatically generate markers for events that happened in a particular game. Using those, I could quickly create clips of those events.

*Estimate: Small*

### Write an OpenRA AI

This one I found on Hacker News: Guidelines for writing an AI player for the OpenRA game. I've led a project that worked on OpenRA in the past, so this open-source game is always of interest to me.

The goal would be to write a really simple AI. Nothing fancy. But let's see where we could go from there.

*Estimate: Medium*

-----

(To be continued.)

This is a living document. Once new ideas arise, I will add them here. Besides, as mentioned earlier, I'm going to update the respective section once I make progress on any of the ideas.
