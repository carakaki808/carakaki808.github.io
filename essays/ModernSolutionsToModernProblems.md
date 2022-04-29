---
layout: essay
type: essay
title: Modern Solutions To Modern Problems
date: 2022-04-28
labels:
  - Software Engineering
  - Learning
  - Design Patterns
  - OOP
---

## The Wheel

One of the earliest known inventions is the wheel. There's evidence that wheels existed as early as 4500 BCE, that’s a really long time ago! It’s a simple design involving a circular object intended to rotate around an axle bearing. Everyone has probably witnessed a wheel used in some form from cars, bikes, and even common household tools like hand trucks.

## The Right Solution

Here’s an easy question. Between a round wheel and a square wheel, which would be more practical for use on a bicycle? Hopefully, the round wheel was the obvious choice. Why do we know this? Probably because we’ve all driven, rode, or have pushed objects with wheels. We know for a fact that wheels work and so do the engineers who design cars. Thus a common **design pattern** is to use round wheels on cars and bikes.

### The Programmer's "Wheel"

Software engineers use design patterns as tried and tested methods to solve problems that occur during the design process. Just like the wheel, these patterns are used again and again because we know they work! For object-oriented programming, patterns will typically involve interactions between objects. These patterns are seen at all levels of the design process and are often reused to satisfy some higher-level objective.

## Patterns In Practice

A common design pattern is that of the **factory pattern**. It’s an object creation pattern. A **factory method** is called on to interact with some specified class-creating object. The class typically has a constructor that builds the object with specific properties. Here is a snippet from code used in an application I’m testing. I make a call to the `isDisplayed` method (seen in the top picture, line 35) which exists in the LandingPage class (seen in the bottom picture, line 10). The method uses functions available in the testcafe library to check if a specific page based on the `pageSelector` and pageId properties (bottom picture, line 4) is being displayed. The factory in this case is the LandingPage class (bottom picture) which interacts with the test function (top picture) when `isDisplayed` is called on.
