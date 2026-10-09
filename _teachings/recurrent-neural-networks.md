---
layout: course
title: Recurrent Neural Networks and LSTMs
description: Seminar in Applied Machine Learning. Feed-forward revision, recurrence, vanishing gradients, and LSTMs.
instructor: Ehsan Moradi, seminar
year: 2025
term: Spring
course_id: rnn-seminar-2025
schedule:
  - week: 1
    date: Spring 2025
    topic: Feed-forward revision
    description: >
      A short revision of ordinary neural networks, the sequence problem they do not fit, and activation functions, before the recurrent model.
  - week: 2
    date: Spring 2025
    topic: Recurrent networks
    description: >
      The recurrent architecture, where it is used, a worked example, and how a step reuses the previous hidden state.
  - week: 3
    date: Spring 2025
    topic: Gradients
    description: >
      A normal gradient, a gradient that grows without bound, and a gradient that vanishes. This is the reason the plain recurrent net is hard to train on long sequences.
  - week: 4
    date: Spring 2025
    topic: LSTM
    description: >
      Long short-term memory as the fix for that training problem. The slides cite StatQuest and Andrew Ng's sequence-models course.
    materials:
      - name: Slides (PDF)
        url: /assets/pdf/teaching/ehsan-moradi-rnn-seminar.pdf
---

Spring 2025, Applied Machine Learning, Amirkabir University of Technology. The talk is *An Introduction to Recurrent Neural Networks (and beyond!)*, 67 slides. I gave it as a seminar in the course, the term before I was a teaching assistant for it.
