---
title: Workshop - Unit Testing with .NET - 2024.07.21
draft: false
tags:
  - software-development
  - back-end
  - dotnet
  - csharp
---
## Preface

This is the script for the workshop I presented at [[Wake Experience]], a division of [[LWSA]] (formerly Locaweb), on July 31, 2024. At the time, I was working as a Software Developer Specialist at this company.

## Introduction

Todo...

## Testing Pyramid

The [[Testing Pyramid]] is a metaphor for thinking about testing in software. [[Mike Cohn]] came up with this concept in his book [[Succeeding with Agile]]. It's a great visual representation that helps us think about different layers of testing. It also tells you how much testing to do on each layer [[#1]] [[#2]].


![[Test Pyramid.png]]_The Test Pyramid (adapted)_

The Test Pyramid offers a rule of thumb for establishing the test suite [[#1]]:
1. Write tests with different granularity.
2. The more high-level you get the fewer tests you should have.

## References

### 1
H. Vocke. “The practical test pyramid.” martinfowler.com. Accessed: Jul. 28, 2024. [Online.] Available:
https://martinfowler.com/articles/practical-test-pyramid.html

### 2
T. Fernandez and D. Ackerson. “The Testing Pyramid: How To Structure Your Test Suite.” semaphoreci.com. Accessed: Jul. 28, 2024. [Online.] Available: https://semaphoreci.com/blog/testing-pyramid