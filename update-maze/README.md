### Project **Maze Game** - Maze Update Function Development and Git Workflow Guide

#### Introduction

This document serves as both a specification for the development of the `maze_update` function within the Maze Game project and a guide to the Git workflow that should be adopted for collaborative and orderly development.

### Function Specification

#### **Update Maze Function**

**Description:**
Updates the maze based on the player's move.

**Inputs:**

- `currentX`: Integer for the player's current horizontal position.
- `currentY`: Integer for the player's current vertical position.
- `maze`: A `width` x `height` array as previously defined.
- `deltaX`: Integer indicating the change in horizontal position.
- `deltaY`: Integer indicating the change in vertical position.

**Outputs:**

- `currentX`: Updated horizontal position.
- `currentY`: Updated vertical position.
- `maze`: Updated `width` x `height` array reflecting the new player's and potentially treasure's positions.

**Comments/Style:**

- Follow the style guideline described in `STYLE.md` within the project repository to maintain code consistency.

### Test-Driven Developmen (TDD) Approach

#### **Folder Structure**

- Code implementation should be placed within the `/src/` subfolder.
  Corresponding unit tests should be organized within the `/tests/` folder.

#### **TDD Guidelines**

- Follow the introductory TDD principles covered in the [previous project](https://github.com/css-software-engineering-studio/sample-tdd).
- Before writing implementation code, write tests that define and validate what the code will do.
- Regularly run tests to ensure new changes do not break existing functionality.
- Use tests to document assumptions and expected behaviors in the code for future reference.
- Your unit tests will co-act as error-checking of your implementation

### Git Workflow Instructions

#### Basic Git Operations

##### 1. **Cloning the Repository**

To start, clone the repository to create your local development environment.

```
git clone [repository URL]
```

##### 2. **Branching Strategy**

###### Team Leader Responsibilities

- A **feature branch** named `maze_update_feature` should be created by the team leader as the main branch for this specific function's development.
  ```
  git checkout -b maze_update_feature
  ```
- Team members will then create individual **subbranches** for their tasks which will initially merge into the `maze_update_feature` branch.
  ```
  git checkout -b [specific_task_branch]
  ```

###### Team Members

- Perform all task-related changes within your subbranches.
- Regular commits should reflect incremental changes:
  ```
  git add .
  git commit -m "concise description of the update"
  ```

##### 3. **Pull Requests**

- Ensure all pull requests in your team are made to the `maze_update_feature` branch, not directly to the main branch.
- Utilize the following guide for changing the base branch for pull requests: [Github Guide on Changing Base Branch](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/changing-the-base-branch-of-a-pull-request)

##### 4. **Handling Merge Conflicts**

- Part of the learning objectives is to engage with merge conflicts as they arise during the process of merging branches.
- If you encounter any merge conflicts as you proceed, here is a suggested tutorial you can follow for [How to Fix Merge Conflicts in Git](https://www.freecodecamp.org/news/how-to-fix-merge-conflicts-in-git/)

#### Final Integration

- After completing all tasks and ensuring functionality through testing, make a final pull request from `maze_update_feature` to the main branch.
- This process should involve careful review to ensure a seamless integration.

#### Incremental Improvement and MVP Development

- Teams are encouraged to pursue the Minimum Viable Product (MVP) strategy; submit basic functional components first.
- If done early, enhancements and creative additions can follow through subsequent branch updates and pull requests.