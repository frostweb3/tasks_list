# ICP Task Manager

This project is an example task manager built on the Internet Computer (ICP) platform. It provides functionality to add, edit, retrieve, and remove tasks. The project is implemented using the Motoko programming language and utilizes various base libraries for data structures and operations.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Examples](#examples)

## Introduction

The ICP Task Manager is designed to help you manage your tasks efficiently. It provides a simple yet powerful interface to add, edit, retrieve, and remove tasks. Each task consists of a title, creation timestamp, and last edit timestamp.

The project utilizes the following base libraries for its implementation:
- `mo:base/HashMap`: Provides a hash map data structure to store tasks.
- `mo:base/Hash`: Implements hashing functions used for key generation in the hash map.
- `mo:base/Iter`: Offers utility functions for working with collections and iterators.
- `mo:base/Time`: Provides time-related functions to capture task creation and edit timestamps.
- `mo:base/Nat`: Implements operations and conversions for natural numbers.
- `mo:base/Text`: Offers text manipulation functions used for task titles.

## Getting Started

To get started with the ICP Task Manager project, follow these steps:

1. Ensure you have the necessary dependencies and development environment set up for Internet Computer (ICP) development.
2. Clone the project repository to your local machine.
3. Do `npm install` in the directory
4. Deploy the project to the Internet Computer using the `dfx deploy` command:

   ```shell
   dfx deploy
   ```

   This will build and deploy the project canisters to your local Internet Computer environment.

5. Once deployed, you can interact with the task manager using the provided API.

## Usage

The ICP Task Manager exposes the following functions through its API:

- `addTask(title: Text)`: Adds a new task with the given title to the task manager. Returns the ID (Nat) of the created task.
- `getTask(taskId: Nat)`: Retrieves the task with the specified ID from the task manager. Returns the task object if found, otherwise returns null.
- `getTasks()`: Retrieves all tasks stored in the task manager. Returns an array of tuples containing the task ID (Nat) and task object.
- `editTask(taskId: Nat, title: Text)`: Modifies the title of the task with the specified ID. Returns a Boolean indicating the success of the operation.
- `removeTask(taskId: Nat)`: Removes the task with the specified ID from the task manager.

## Examples

Here are some examples of how you can call the functions via the dfx command line:

- Add a task:
  ```shell
  dfx canister call task_manager addTask '("Task Title")'
  ```

- Get a task by ID:
  ```shell
  dfx canister call task_manager getTask '(1)'
  ```

- Get all tasks:
  ```shell
  dfx canister call task_manager getTasks
  ```

- Edit a task:
  ```shell
  dfx canister call task_manager editTask '(1, "New Task Title")'
  ```

- Remove a task:
  ```shell
  dfx canister call task_manager removeTask '(1)'
  ```

---
