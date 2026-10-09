---
layout: course
title: Distributed Systems
description: Teaching assistant. Clocks, commitment protocols, and a Paxos programming assignment.
instructor: Dr. Seyyed Ahmad Javadi
year: 2026
term: Spring
course_id: distributed-systems-2026
schedule:
  - week: 1
    date: Homework 1
    topic: Logical time
    description: >
      Vector clocks on a three-process history, then Lamport timestamps and vector timestamps on a four-process diagram, including which events are concurrent. A third question restarts four servers from different logical clocks, taken from the last digits of the student's ID, and asks for the Lamport timestamps of the resulting send, receive, and local events.
  - week: 2
    date: Homework 2
    topic: Atomic commitment
    description: >
      Three-phase commit, and why it avoids leaving participants blocked for an unknown time when the coordinator or another node fails, assuming the network does not partition. Nested two-phase commit: provisional commit of a subtransaction, abort of descendants when a parent aborts, and orphan transactions when a child loses its parent.
  - week: 3
    date: 9 June – 11 July 2026
    topic: Paxos
    description: >
      A programming assignment. The required part is the Paxos synod algorithm for one variable, with proposer, acceptor, and learner in each of three replicas, durable acceptor state, and the RPCs propose(value) and learn(). A bonus part builds the state-machine form, add_command and list_commands, from many concurrent synod instances. Students may choose the language. An existing Paxos library is not allowed.
---

Spring 2026, Department of Computer Engineering. Dr. Seyyed Ahmad Javadi taught the course. I was one of four teaching assistants. The assignments below are the ones in the course packet I worked from, together with the submitted homework I graded.

The lecture set for the course runs from an introduction through Hadoop, vector clocks and mutual exclusion, Spanner, broader consistency semantics, and scheduling. Homework 1 sits on the clock material. The project sits on consensus.
