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
<img class="ui small floated right image" src="../images/Roue_primitive.png">
One of the earliest known inventions is the wheel. There's evidence that wheels existed as early as 4500 BCE, that’s a really long time ago! It’s a simple design involving a circular object intended to rotate around an axle bearing. Everyone has probably witnessed a wheel used in some form from cars, bikes, and even common household tools like hand trucks.

## The Right Solution

Here’s an easy question. Between a round wheel and a square wheel, which would be more practical for use on a bicycle? Hopefully, the round wheel was the obvious choice. Why do we know this? Probably because we’ve all driven, rode, or have pushed objects with wheels. We know for a fact that wheels work and so do the engineers who design cars. Thus a common **design pattern** is to design cars with round wheels.<img class="ui small floated right image" src="../images/Toyota_Motor_Plant_in_1950s.jpg">

### The Programmer's "Wheel"

Software engineers use design patterns as tried and tested methods to solve problems that occur during the design process. Just like the wheel, these patterns are used again and again because we know they work! For object-oriented programming, patterns will typically involve interactions between objects. These patterns are seen at all levels of the design process and are often re-used to satisfy some higher-level objective.

## Patterns In Practice

A common design pattern is that of the **factory pattern**. It’s an object creation pattern. A factory method is called on to interact with some specified class-creating object. The class typically has a constructor that builds the object with specific properties. Here is a snippet from code used in an application I’m testing.

```

test('Test that landing page shows up', async (testController) => {
  await landingPage.isDisplayed(testController);
});

```

```

class LandingPage {
  constructor() {
    this.pageId = '#landing-page';
    this.pageSelector = Selector(this.pageId);
  }

  /** Asserts that this page is currently displayed. */
  async isDisplayed(testController) {
    // This is first test to be run. Wait 10 seconds to avoid timeouts with GitHub Actions.
    await testController.wait(60000).expect(this.pageSelector.exists).ok();
  }
}

```

First, a call is made to the `isDisplayed` method (seen in the top block) which exists in the LandingPage class (seen in the bottom block). The method uses functions available in the testcafe library to check if a specific page based on the `pageSelector` and pageId properties (bottom block) is being displayed. The factory in this case is the LandingPage class (bottom block) which interacts with the test function (top block) when `isDisplayed` is called on.

## Summary

In the sample code above, the problem was that I needed to test if a page was being displayed. The design pattern I used was a factory pattern to implement a method to test if a particular page exists. The `isDisplayed` method can be re-used as a preliminary test before testing other components that require the page to be displayed as a prerequisite. Overall, design patterns allow users to design tried and true solutions for most programming problems.
