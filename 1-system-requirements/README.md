# System requirements

1.  What are the functional and non-functional requirements
1.  Why are they so important

[**functional requirements**](#1-functional-requirements)

> Define system **behavior**, what a system is supposed to do

example:

1. The system must allow applications to exchange messages

[**non-functional requirements**](#2-non-functional-requirements)

> Defines the **qualities** of a system how a system is supposed to be

Example:

1. Scalable
1. Highly available
1. Fast

**interviewer**

> Let me state the problem ambigously and see how the candidate approaches it

**interviewee**

> The problem seems too big. I should try to define specific functions and reduce the scope

> Also, I need ot figure out non-functional requirements and use my knowledge of system design concepts and patterns to address each requirement.

Hmm.. Let me think...

> Here are some fundamental concepts that help design scalable, highly available, and fast systems

1. Scale writes

   1. hash-based partitioning
   1. Bounded queue
   1. append-only logs
   1. emedded database
   1. B-tree database
   1. LSM-tree database

1. Scale reads

   1. push vs pull
   1. long polling

1. availability

   1. leader-based replication
   1. leaderless replication
   1. leader election
   1. coordination service
   1. cstring consistency
   1. load shedding
   1. rate limiting
   1. shuffle sharding
   1. reverse proxy
   1. service discovery
   1. request routing

1. fast

   1. bathcing
   1. Compression

The most important thing to remember is that the interview is your team mate and should help you decide what decision to make.

**Interviewer**

> I will help you define requirements.

> I do interviews to hire, not to reject

> My goal is to collect data points, not see you get stucka nd suffer

**summary**

1. Define functional requirements
1. Define non-functional requirements
1. Order non-functional requirements according to their importance
1. use this list as a tie breaker considering multiple design options and trade-offs

## 1. Functional requirements

1. How to define functional requirements
1. Working backwards approach

**how to define functional requirements**

> Start with the customer and work backwards

1. Who are the customers
1. How will they use the systems

ex. for youtube

1. Youtube users/customers

   1. Content creators
   1. Content viewers

1. How do the customers use the sytems
   1. Content creators
      1. upload videos
      1. create posts
      1. view analytics
   1. Content viewers
      1. search for videos
      1. watch videos
      1. leave comments

For entry positions the interviewer may be more specific, for seniors the questions may be more ambiguious. The interviewer want to see how you deal with ambiguos questions, break it down to smaller manageable pieces

> Let's design a YouTube-like system. Here are the use cases. Let's convert them to API first.

1. Upload a video to the channel
1. Return a list of videos for the channel, ordered by popularity
1. Search for videos and channels
1. Watch the specific video
1. Delete the specific video

## 2. Non-Functional requirements

Types of non-functional requirements

1. [High availability](./01-high-availability.md)

2. [Fault tolerance, resilience, reliability](./02-fault-tolerance.md)

3. [Scaling](./03-scalability.md)

4. [Performance](./04-performance.md)
