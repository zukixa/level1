## Project **Maze Game** - Function create_maze Development and Git Workflow Guide

## Introduction

This document serves as both a specification for the development of the `create_maze` function within the Maze Game project and a guide to the Git workflow that should be adopted for collaborative and orderly development.

## **create_maze Function**

**Description:**
Generates a new maze layout.

**Inputs:**

- `width`: Even integer number of characters for the maze’s width.
- `height`: Even integer number of characters for the maze’s height.
- `boulders`: Integer indicating the number of obstacles to randomly place in the maze.

**Output:**

- `maze`: A `width` x `height` array of characters with:
  - 'A' at `(0, 0)`.
  - 'T' at `(width-1, height-1)`.
  - '\*' asterisks representing boulders, randomly placed.
  - ' ' spaces placed everywhere else, representing "safe" spaces.

**Comments/Style:**

- Follow the style guideline described in [`STYLE.md`](https://github.com/zukixa/level1/blob/main/STYLE.md) within the project repository to maintain code consistency.
- You don’t need to ensure there is a path between ‘A’ and ‘T’
- It’s okay for ‘A’ and ‘T’ to overwrite boulders
- It’s okay for boulders to overwrite boulders (not necessary to have exactly “boulders” number of boulders)
- Emojis can replace 'A', 'T', and '\*' symbols.

## Test-Driven Developmen (TDD) Approach

## **Folder Structure**

- Code implementation should be placed within the `/src/` subfolder.
  Corresponding unit tests should be organized within the `/tests/` folder.

## **TDD Guidelines**

- Follow the introductory TDD principles covered in the [previous project](https://github.com/css-software-engineering-studio/sample-tdd).
- Before writing implementation code, write tests that define and validate what the code will do.
- Regularly run tests to ensure new changes do not break existing functionality.
- Use tests to document assumptions and expected behaviors in the code for future reference.
- Your unit tests will co-act as error-checking of your implementation

## Git Workflow Instructions

## Basic Git Operations

### 1. **Cloning the Repository**

To start, clone the repository to create your local development environment.

```
git clone [repository URL]
```

### 2. **Branching Strategy**

### Team Leader Responsibilities

- A **feature branch** named `create_maze_feature` should be created by the team leader as the main branch for this specific function's development.
  ```
  git checkout -b create_maze_feature
  ```
- Team members will then create individual **subbranches** for their tasks which will initially merge into the `create_maze_feature` branch.
  ```
  git checkout -b [specific_task_branch]
  ```

### Team Members

- Perform all task-related changes within your subbranches.
- Regular commits should reflect incremental changes:
  ```
  git add .
  git commit -m "concise description of the update"
  ```

### 3. **Pull Requests**

- Ensure all pull requests in your team are made to the `create_maze_feature` branch, not directly to the main branch.
- Utilize the following guide for changing the base branch for pull requests: [Github Guide on Changing Base Branch](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/changing-the-base-branch-of-a-pull-request)

### 4. **Handling Merge Conflicts**

- Part of the learning objectives is to engage with merge conflicts as they arise during the process of merging branches.
- If you encounter any merge conflicts as you proceed, here is a suggested tutorial you can follow for [How to Fix Merge Conflicts in Git](https://www.freecodecamp.org/news/how-to-fix-merge-conflicts-in-git/)

### 5. **Integration into Main**

- Once all tasks are done and the tests are passed, create a pull request from the `create_maze_feature` branch to the main branch.
- Review the changes carefully to ensure the new features blend well with the existing code.

### 6. **Incremental Improvement and MVP Development**

- Start with a Minimum Viable Product (MVP) approach by integrating the basic functions into the main branch first. This sets a functional base early in the project.
- Focus initially on core features to establish foundational functionality, allowing for early testing and feedback.
- After stabilizing the base, gradually add more complex features or enhancements through additional updates and pull requests. This step-by-step approach helps manage risks and improves the product over time.
