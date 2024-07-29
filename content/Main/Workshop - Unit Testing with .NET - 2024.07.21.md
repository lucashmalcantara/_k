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

Regarding the Test Pyramid, it is also important to highlight that the higher the layer:
-   More effort.
-   Slower.
-   Higher maintenance.


![[Test Pyramid.png]]_The Test Pyramid (adapted)_

The Test Pyramid offers a rule of thumb for establishing the test suite [[#1]]:
1. Write tests with different granularity.
2. The more high-level you get the fewer tests you should have.

## Unit tests

[[Unit Testing|Unit tests]] are used to test isolated software components, such as individual class methods [[#5]]. Here are the main points about unit testing [[#1]] [[#3]]:
- The base of the test suite is composed of unit tests.
- It tests the **smallest part of the code**: function/method.
- **More numerous** than any other type of test.
- **Should be fast** (execution in milliseconds).
- Should avoid accessing databases, file systems, or HTTP requests (using mocks and stubs for these parts).
- Tests public interfaces, not private methods.
- When to use? It is used in all classes with production code, regardless of their functionality or which layer they belong to.

> It is the **most important class of tests** because it is **quick to develop**, requires **little maintenance**, provides **fast feedback**, and helps with **code documentation**.

## Integration tests

[[Integration Testing|Integration tests]] evaluate a software's components on a broader level than [[Unit Testing|unit tests]] [[#5]]. Here are the main points about integration testing [[#1]] [[#4]] [[#5]]:

- Integration tests confirm that two or more software components work together to produce and expected result.
-  Can be broad (broad integration test) or narrow (narrow integration test).
	- **Narrow integration test** (*teste de integração estreito*, in Portuguese): when writing narrow integration tests, you should aim to **run external dependencies locally**, using local instances or fake versions of services to mimic real interactions.
	- **Broad integration test** (*teste de integração abrangente*, in Portuguese): broad integration tests **require live versions of all services** and substantial test environment and network access, exercising code paths through all services, not just interactions.
- **Prefer to perform integration tests as narrowly as possible** by replacing services and databases with test doubles.
- Can be **more complex** to write than small, isolated unit tests.
- Provides the advantage of **greater confidence** that the software will function correctly when integrating various components.
- Should be used primarily when there is a need for data serialization or deserialization.

## End-to-End (E2E) tests 

[[End-to-end (E2E) testing]] evaluates an application's entire workflow, from start to finish, integrating all components and services [[#6]]. Here are the main points about integration testing [[#1]]:

- Among various testing methods, E2E testing offers the **highest level of assurance** that the software is functioning correctly.
- However, it is prone to **several issues**, often failing due to unexpected and unpredictable factors. These tests can frequently **yield false positives**, caused by network failures, browser-specific quirks, or runtime issues.
- Due to its **high maintenance** costs and slower execution, e2e testing should be minimized.
- When to use it? Employ E2E testing for **high-value user integrations**. For instance, in an e-commerce site, it is critical for testing the entire process of adding items to the cart and completing the checkout.

> Remember: you have lots of lower levels in your test pyramid where you already tested all sorts of edge cases and integrations with other parts of the system. There's no need to repeat these tests on a higher level. High maintenance effort and lots of false positives will slow you down and cause you to lose trust in your tests, sooner rather than later.
> 
> H. Vocke, 2018


## Test Doubles

TODO...

## References

### 1

H. Vocke. “The practical test pyramid.” martinfowler.com. Accessed: Jul. 28, 2024. [Online.] Available:
https://martinfowler.com/articles/practical-test-pyramid.html

### 2

T. Fernandez and D. Ackerson. “The Testing Pyramid: How To Structure Your Test Suite.” semaphoreci.com. Accessed: Jul. 28, 2024. [Online.] Available: https://semaphoreci.com/blog/testing-pyramid

### 3

A. Okazaki. "Teste UNITÁRIO, teste de INTEGRAÇÃO e teste FUNCIONAL: QUANDO e COMO USAR?" youtube.com. Accessed: Jul. 28, 2024. [Online.] Available: https://youtu.be/35nlBX5_GzE

### 4

M. Fowler. “Integration Test.” martinfowler.com. Accessed: Jul. 28, 2024. [Online.] Available: [Integration Test (martinfowler.com)](https://martinfowler.com/bliki/IntegrationTest.html)

### 5

Microsoft. “Integration tests in ASP.NET Core.” microsoft.com. Accessed: Jul. 28, 2024. [Online.] Available: https://learn.microsoft.com/en-us/aspnet/core/test/integration-tests?view=aspnetcore-8.0

### 6

F. Bellato. “A Evolução dos testes E2E no Zé Delivery.” medium.com. Accessed: Jul. 28, 2024. [Online.] Available: https://medium.com/rez%C3%A9nha/a-evolu%C3%A7%C3%A3o-dos-testes-e2e-no-z%C3%A9-delivery-894ac3781bbf

### 7

T. Fernandez and D. Ackerson. “The Testing Pyramid: How to Structure Your Test Suite.” semaphoreci.com. Accessed: Jul. 28, 2024. [Online.] Available: https://semaphoreci.com/blog/testing-pyramid
