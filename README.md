# Refactoring legacy code

Legacy code can be complex. It often starts simple, but collects complexity as the product and its customers evolve.

This repository has legacy code in it. Let's refactor to enable evolution without adding complexity.

## About this repository

The objective of the code is to monitor battery temperature and prevent damage:

- Classify the temperature measurement as being too high or too low. This classification depends on the type of cooling. With active cooling, the battery can reach higher temperatures before taking action.
- Transmit the classification to take action: When the system has a controller, send the classification to it. In the absence of a controller, send the classification via email. In this project, the transmission is 'simulated' by printing on the console.

The [GitHub Actions](https://docs.github.com/en/actions) in this project implement several workflows:

- No Duplications: Fails on finding duplication of 3 lines or more. There are no duplications, so this passes.
- Limit complexity: The limit per function is set at 3 and it's currently failing
- Build and Run: Runs the tests. It's passing currently, but there are hardly any tests. You need to add more.
- Enter Reflections: Replace the enter in the **Reflections** section below, within this file. This workflow fails till you replace it with your impressions.

As with any legacy, have a look at the code to understand it better.

This project uses the
[GTEST](https://google.github.io/googletest/)
to test functionality.

The 'Build and Run' workflow stores coverage-data as an artifact in the workflow run. You can download it from GitHub Actions.

## The refactoring task

Cyclomatic complexity is high in a few places. This indicates potential to steadily increase, as customers ask for changes and new features. Reduce the cyclomatic complexity. In future, it must be possible to add new features with less code-changes and re-testing.

Code coverage is low, because the test code is incomplete. Write more tests to take care of the variations. Track and improve the coverage.

Uncovered lines indicate an opportunity to write tests. Complex and repetitive tests indicate opportunity to simplify the code.

> Caution: High coverage doesn't indicate absence of bugs!

## Reflections

This section is about your regular work / project, not about the code in this repository.

Think about guiding refactoring-work in your regular/project teams. Think of the day-to-day work done in your team, and improving the quality of code.

You have seen a few workflows in this repository. They are quality-gates to prevent duplication, control complexity and prove functionality. Do you think some of them have potential to guide code-improvements in your team?  yes

During the next four weeks, what improvement do you plan in your code-quality practice? (in your regular work, not in this repository!)

Over the next four weeks, I aim to elevate the quality of my code by concentrating on the following practices:

1. Modular Code Structure: I'll work on breaking down my code into smaller, independent modules to make it more manageable and easier to build upon. Keeping CCN in mind and loc less as possible.
2. Bug Detection via Testing: I'll focus on identifying bugs through thorough testing, making sure that all edge cases and scenarios are carefully tested.
3. Adoption of Test-Driven Development (TDD): Embracing TDD will be central to my approach, as it involves writing tests before implementing the code, resulting in more dependable and well-structured code.
4. Enhanced Testing Strategies: I'll aim to refine my testing methods to ensure tests are comprehensive, meaningful, and cover a wide variety of scenarios. sp that all possible tests are covered aiming 100%- code coverage.
5. Consistent Code Reviews: I plan to implement regular code reviews for all code, which will help identify issues early and reinforce good coding practices across the team.
6. Emphasis on Pure Functions: Writing pure functions will be a priority, as they improve the code's readability and make testing simpler and more straightforward.
