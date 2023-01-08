---
title: Clean Coding
tags: [Software Development, Clean Code]
style: fill
color: info
description: These four “clean code” tips will dramatically improve your engineering team’s productivity
---

Source: [Jonathan Fulton](https://engineering.videoblocks.com/these-four-clean-code-tips-will-dramatically-improve-your-engineering-teams-productivity-b5bd121dd150)

A few years ago at VideoBlocks we had a major code quality problem: “spaghetti” logic in most files, tons of duplication, no tests and more. Writing new features and even minor bug fixes required a couple of Tums at best and entire bottles of Pepto-Bismol and Scotch far too often. Our WTFs per minute were sky-high.

{% include elements/figure.html image="https://cdn-images-1.medium.com/max/1600/1*J2mKSLBEp_jUbMtOWXTTjQ.png" caption="Several years ago we were definitely in the room on the right but we’ve moved a lot closer to the room on the left." %}

Today, the overall quality of our codebases are significantly better thanks in large part to a deliberate effort to improve code quality. A couple ago when we identified the problem, we read Robert Martin’s Clean Code as a team and did our best to implement his recommendations and even introduced “clean code” as a core cultural tenant for the engineering team. I highly recommend doing both as you start scaling. Implementing “clean code” practices appropriately will double productivity in the long run (at a bare minimum) and significantly improve moral on the engineering team. Who wants to be in the room on the right given the choice?

Out of all the ideas we implemented from Clean Code and other sources, five provided at least 80% of the gains in productivity and team happiness.
