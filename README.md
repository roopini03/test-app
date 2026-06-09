---
name: Readme Creator
model: gpt-4.1
temperature: 0.2
toolkits:
  - type: github
---

# Quiz CLI

An interactive command-line quiz game for learning JavaScript and Node.js fundamentals.

## Overview

Quiz CLI is a terminal-based educational game built with Node.js and ES modules. It loads quiz questions from a JSON file, lets users choose a category and question count, and then presents multiple-choice questions one at a time with instant feedback, progress tracking, and a final score summary.

The project is intentionally lightweight and uses only built-in Node.js modules. It is designed to demonstrate common JavaScript and Node.js concepts such as asynchronous file reading, modular code organization, readline-based input handling, and class-based application logic.

## Features

- Interactive command-line quiz experience
- Multiple quiz categories:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Selectable question count per session
- Shuffled questions for replayability
- Instant correctness feedback after each answer
- Explanations shown for each question
- Progress bar and percentage tracking
- Final results summary with performance message
- Review section for incorrect answers
- ANSI color output without external dependencies

## Requirements

- Node.js 18 or later
- A terminal or command prompt that supports standard ANSI escape codes

## Setup

1. Clone the repository.
2. Move into the project directory:
   ```bash
   cd test-app
   ```
3. Install dependencies:
   ```bash
   npm install
   ```

> Note: There are no external runtime dependencies, but running `npm install` will still prepare the project as a standard Node.js app.

## Usage

Start the quiz with:

```bash
npm start
```

Or run the entry file directly:

```bash
node index.js
```

### How it works

1. Choose a quiz category.
2. Choose how many questions to answer.
3. Answer each multiple-choice question by entering the option number.
4. Review your score and explanations at the end.
5. Choose whether to play again.

### Example flow

```text
Choose a category:
1. JavaScript Basics
2. Node.js Fundamentals
3. General Programming

How many questions?
1. All questions
2. 3 questions
3. 5 questions

Your choice (enter number): 1
```

## File Structure

```text
.
├── index.js
├── package.json
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### Key files

- `index.js` — application entry point, loads questions, drives the quiz loop, and handles the main user experience
- `src/input.js` — readline helpers for prompting, selecting options, confirmations, and pause behavior
- `src/quiz.js` — quiz game logic, scoring, progress tracking, and results display
- `src/colors.js` — ANSI color utilities for styled terminal output
- `data/questions.json` — quiz content organized by category
- `package.json` — project metadata, scripts, and Node.js engine requirement

## Code Structure and Behavior

### `index.js`

The main application file:

- reads quiz data from `data/questions.json`
- builds category options from the loaded JSON
- creates a `Quiz` instance for the selected category
- loops through questions until the quiz is complete
- shows final results and prompts the user to play again

### `src/input.js`

Provides reusable terminal input helpers:

- `createInterface()` — creates a readline interface
- `prompt()` — wraps readline input in a Promise
- `select()` — displays numbered options and validates selection
- `confirm()` — handles yes/no prompts
- `pressEnter()` — pauses execution until Enter is pressed

### `src/quiz.js`

Contains the quiz logic:

- shuffles questions using the Fisher-Yates algorithm
- tracks current question index, score, and answers
- validates user responses
- prints per-question feedback and explanations
- calculates final percentage and performance message
- lists incorrect answers for review

### `src/colors.js`

Defines simple ANSI color helpers such as:

- `success()`
- `error()`
- `warning()`
- `info()`
- `highlight()`

## Data Format

Quiz questions are stored in `data/questions.json` using this structure:

```json
{
  "categories": {
    "category-id": {
      "name": "Category Display Name",
      "questions": [
        {
          "question": "Question text",
          "options": ["A", "B", "C", "D"],
          "answer": 2,
          "explanation": "Why this answer is correct"
        }
      ]
    }
  }
}
```

### Important fields

- `question` — the question shown to the player
- `options` — array of answer choices
- `answer` — zero-based index of the correct option
- `explanation` — optional clarification shown after answering

## Scripts

Available npm scripts from `package.json`:

- `npm start` — runs the application
- `npm test` — runs the Node.js test runner (`node --test`)

## Development Notes

This project demonstrates several JavaScript and Node.js concepts, including:

- ES modules (`import` / `export`)
- async/await
- Promises
- file system access via `node:fs/promises`
- terminal input with `node:readline`
- class-based design
- array methods such as `map`, `filter`, `forEach`, and `slice`
- destructuring assignment
- template literals
- error handling and cleanup in `finally`

## Contributing

Contributions are welcome. A simple workflow would be:

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the application with `npm start`.
5. Submit a pull request.

If you add or change quiz questions, keep the JSON structure in `data/questions.json` consistent.

## License

This project is licensed under the MIT License.
