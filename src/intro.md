# Introduction

Welcome to **FRC Programming**! This guide aims to give you a basic understanding of how robots in FRC are programmed, helping you get up-to-speed quickly on the fundamentals.
It also aims to be useful as a reference if you need to brush up on something you haven't touched in a while.

Start with a [coding-focused overview of FRC][overview], or use the sidebar to jump to a specific section.

[overview]: overview.md

## Prerequisites

This guide assumes the following:

- General understanding of object-oriented programming and inheritance
  - Note: knowledge of a specific language is not required.
    Examples will be given in [pseudocode] whenever possible to keep this guide language-independent.
    Some examples will be given in Java as comprehensive, real-world demonstrations.
- All other assumed knowledge is kept to a minimum

[pseudocode]: https://en.wikipedia.org/wiki/Pseudocode

## Why This Guide

There are plenty of other resources on FRC Programming available, such as
[WPILib's official documentation][wpilib-docs], [Emory Robotics' FRC Programming Guide][emory-guide],
[r/FRC_PROGRAMMING][r-frcprogramming], [team 5687's guide][5687-guide], or just google for more.
However, this guide has a few explicit goals that other resources tend not to fulfill:

- *Avoid jargon.* Some resources use a lot of technical terms without first explaining them.
- *Be structured.* Some resources have great information, but don't structure it in a way such that a beginner can easily learn.
- *Be language-independent.* Some resources focus specifically on Java or C++, rather than on the concepts that are shared across all WPILib languages.
- *Give lots of diagrams and code examples.* Some resources give only large blocks of text or long videos, without any alternative forms of presenting the information.
- *Explain why.* Some resources give great explanations on current conventions and best-practices, but don't explain their purpose or what problems they avoid.

[wpilib-docs]: https://docs.wpilib.org/en/stable/index.html
[emory-guide]: https://github.com/Emory-Robotics/FRC-Programming-Guide
[r-frcprogramming]: https://www.reddit.com/r/FRC_PROGRAMMING/
[5687-guide]: https://github.com/frc5687/2021-tutorial

## A Word on Coding Style

WPILib code often follows particular naming choices, such as prefixing class variable names with `m_` and beginning enum option names with `k`.
This guide makes no attempt to follow these conventions, as not all teams stick to them
and they would only distract from the intent of the code examples.
When writing robot code, programmers should use whichever naming conventions are used within their team.

## Contributing

This guide is free and open-source. You can find the source on [GitHub] and open and issue or submit a pull request to suggest a change.

[GitHub]: https://github.com/JoeWildfong/frc-programming
