# Quiz CLI

## Overview
Quiz CLI is an interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts. It uses Node.js built-in modules, ES modules, and a simple terminal UI to present questions, accept answers, score the player, and show results.

## Features
- Interactive terminal quiz flow
- Multiple quiz categories
- Selectable question count per round
- Randomized question order
- Score tracking and feedback messages
- Review of incorrect answers at the end
- Colorized terminal output with ANSI escape codes
- No external dependencies

## Requirements
- Node.js 18 or later

## Setup
1. Clone the repository.
2. Open the project folder.
3. Install dependencies if needed. This project has no external npm packages, so there is nothing to install.
4. Run the app with Node.js.

## Usage
Start the quiz from the project root:

```bash
npm start
```

Or run directly:

```bash
node index.js
```

### How it works
1. Choose a quiz category.
2. Choose how many questions to answer.
3. Answer each multiple-choice question by entering the option number.
4. Review your score and incorrect answers.
5. Choose whether to play again.

## Scripts
Defined in `package.json`:

- `npm start` - Runs the quiz CLI with Node.js
- `npm test` - Runs Node.js tests with the built-in test runner

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

### Key Files
- `index.js` - Application entry point and main game loop
- `src/input.js` - Readline-based input helpers
- `src/quiz.js` - Quiz logic, scoring, and result display
- `src/colors.js` - ANSI color helpers for terminal output
- `data/questions.json` - Quiz categories and question bank

## How It Works
### `index.js`
- Loads quiz questions from `data/questions.json`
- Displays the welcome banner
- Lets the user choose a category and question count
- Starts the quiz session
- Shows results and asks whether to play again

### `src/input.js`
Provides reusable helpers for:
- creating a readline interface
- prompting for text input
- selecting from a numbered list
- confirming yes/no prompts
- waiting for Enter to continue

### `src/quiz.js`
Handles:
- shuffling questions
- tracking progress and score
- checking answers
- showing explanations
- displaying final results and review items

### `src/colors.js`
Provides simple ANSI color utilities such as:
- success messages
- errors
- highlights
- informational text

### `data/questions.json`
Contains three quiz categories:
- JavaScript Basics
- Node.js Fundamentals
- General Programming

Each question includes:
- question text
- multiple-choice options
- correct answer index
- explanation text

## Example Output
A typical session will:
- show a banner
- ask the user to pick a category
- show a numbered list of answers
- display whether the answer is correct
- print the final score and review missed questions

## Testing
Run the test suite with:

```bash
npm test
```

> Note: The project currently includes the Node.js test script, but may not contain dedicated test files yet.

## Contributing
Contributions are welcome. If you want to improve the project:
1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the application.
5. Open a pull request.

## License
This project is licensed under the MIT License.
