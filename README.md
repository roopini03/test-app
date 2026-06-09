---
name: Readme Creator
---

# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts.

Built with modern Node.js features and no external dependencies, this project is a great example of:

- ES modules (`import` / `export`)
- Async/await and Promises
- Node.js built-in modules
- Terminal input handling with `readline`
- Object-oriented programming with classes
- Simple game-state management in a CLI app

## Overview

When you run the app, it presents a terminal-based quiz experience where you can:

1. Choose a quiz category
2. Choose how many questions to answer
3. Answer multiple-choice questions one by one
4. Review your score and incorrect answers at the end
5. Play again if you want another round

The quiz content is stored in JSON, so it is easy to expand with new categories or questions.

## Features

- Interactive terminal UI with colored output
- Multiple quiz categories
- Shuffled questions for replayability
- Progress bar shown during the quiz
- Immediate feedback after each answer
- Final score summary with performance message
- Review section for incorrect answers
- No third-party dependencies

## Requirements

- [Node.js](https://nodejs.org/) **18.0.0 or later**
- npm (included with Node.js)

## Setup

```bash
git clone <repository-url>
cd test-app
npm install
```

> This project does not currently use external packages, so `npm install` is optional, but it is still safe to run and keeps your environment consistent.

## Usage

Start the quiz app:

```bash
npm start
```

Or run it directly:

```bash
node index.js
```

### How to play

- Use the number prompts shown in the terminal
- Enter the number of the answer you want to choose
- Press `Enter` when prompted to continue
- After the final question, review your score and decide whether to play again

## Example Flow

```text
Choose a category:
1. JavaScript Basics
2. Node.js Fundamentals
3. General Programming

How many questions?
1. All questions
2. 3 questions
3. 5 questions
```

Then the app presents each question with numbered options. At the end, you will see:

- Total score
- Percentage result
- A performance message
- A review of any missed questions

## Project Structure

```text
.
├── index.js
├── package.json
├── data
│   └── questions.json
└── src
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File Details

- `index.js` - Application entry point. Loads quiz data, displays the menu, and controls the main game loop.
- `src/quiz.js` - Quiz class and game logic, including scoring, progress, question handling, and results.
- `src/input.js` - Helper functions for terminal input using Node's built-in `readline` module.
- `src/colors.js` - ANSI color utilities for styled terminal output.
- `data/questions.json` - Quiz question bank and categories.
- `package.json` - Project metadata, scripts, and Node.js engine requirements.

## Scripts

- `npm start` - Run the quiz application
- `npm test` - Run the Node.js test runner (`node --test`)

## Data Format

Questions are stored in `data/questions.json` using this structure:

- `categories` object
- Each category has a `name`
- Each category contains a `questions` array
- Each question includes:
  - `question`
  - `options`
  - `answer` (zero-based index)
  - `explanation` (optional)

This makes it easy to add new categories or update content without changing the core application logic.

## Extending the Quiz

To add a new category:

1. Open `data/questions.json`
2. Add a new key under `categories`
3. Provide a display name and a list of questions
4. Make sure each question has the correct answer index

Example:

```json
{
  "categories": {
    "newCategory": {
      "name": "New Category Name",
      "questions": [
        {
          "question": "Example question?",
          "options": ["A", "B", "C", "D"],
          "answer": 0,
          "explanation": "Why A is correct."
        }
      ]
    }
  }
}
```

## Testing

The project includes a `test` script configured for Node's built-in test runner:

```bash
npm test
```

If you add tests, place them in a format compatible with `node --test`.

## Development Notes

- The app uses ES modules, so imports and exports follow modern Node.js syntax.
- `readline` is used to keep the experience fully interactive in the terminal.
- Questions are shuffled on each run for variety.
- The quiz loop tracks progress and stores answer history for the final review screen.
- Terminal colors are handled with ANSI escape codes instead of external libraries.

## Contributing

Contributions are welcome. A good workflow is:

1. Fork the repository
2. Create a new branch for your changes
3. Update quiz content or source code
4. Test your changes with `npm start`
5. Submit a pull request

If you add new features, try to keep the codebase dependency-free unless a package is truly needed.

## License

This project is licensed under the **MIT License**. See `package.json` for details.

## Acknowledgements

This project is a compact example of a modern Node.js CLI application and is ideal for learning:

- Module structure
- CLI interaction
- JSON-driven content
- Basic game state management
- Clean separation of concerns
