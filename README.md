# quiz-cli

> A terminal-based, interactive JavaScript quiz game built with Node.js, ES modules, and JSON-driven quiz content.

## Documentation Metadata

- **Model:** GPT-4.1
- **Temperature:** 0.2

## Project Description

`quiz-cli` is a command-line quiz application designed to help users practice JavaScript and general programming concepts in an interactive way. The app presents a welcome banner, lets the user choose a quiz category and number of questions, and then runs a timed-style interactive quiz flow in the terminal.

This repository is structured as a small but clean Node.js CLI project:

- `index.js` acts as the application entry point and coordinates the quiz flow.
- `src/` contains reusable modules for terminal colors, input handling, and quiz logic.
- `data/questions.json` stores all quiz questions and answer explanations in a structured format.

The project is built around a simple architecture:
- **UI/Styling layer:** terminal colors and formatted output
- **Input layer:** reusable readline helpers for prompts and selections
- **Quiz engine:** core logic for shuffling, scoring, rendering progress, and reviewing answers
- **Content layer:** JSON data that powers the quiz categories and questions

## Repository Structure

```bash
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

### Folder and File Overview

#### `index.js`
Main entry point for the CLI app. It:
- loads quiz questions from `data/questions.json`
- displays the welcome banner
- handles category selection
- handles question count selection
- starts the quiz
- manages replay behavior

#### `src/colors.js`
Terminal styling helpers for ANSI-colored output. These helpers are used to:
- highlight success and error messages
- display warnings and information
- emphasize headings and key values
- keep terminal output readable and visually organized

#### `src/input.js`
Interactive input utilities built on Node.js `readline`. This module provides a reusable way to:
- prompt the user for input
- select from numbered options
- confirm yes/no choices
- pause execution until the user presses Enter

#### `src/quiz.js`
Contains the core quiz engine, likely implemented as a `Quiz` class. This module manages:
- question shuffling
- current question tracking
- score calculation
- progress display
- interactive question prompts
- final results summary
- review of incorrect answers

#### `data/questions.json`
Quiz content source. It stores categorized questions and answer metadata for:
- **javascript** — JavaScript Basics
- **nodejs** — Node.js Fundamentals
- **general** — General Programming

Each question includes:
- `question`
- `options`
- `answer`
- `explanation`

#### `.idea/`
IDE/editor configuration directory. It is not part of the application logic and is typically specific to local development environments.

#### `.DS_Store`
macOS system file. It is not part of the project runtime and can be ignored.

## Key Features

- Interactive terminal quiz experience
- Category-based question selection
- Configurable number of questions per session
- Reusable CLI input helpers
- Colorized terminal output for better readability
- Score tracking and progress feedback
- Final result summary
- Review of incorrect answers with explanations
- JSON-driven quiz content for easy updates and expansion
- Modular ES module-based code organization

## Setup Instructions

### Prerequisites

- **Node.js 18 or higher**

The project uses:
- built-in ES modules
- the Node.js `readline` interface
- `node --test` for testing

### Install Dependencies

If dependencies are not already installed, run:

```bash
npm install
```

> Note: The repository description does not list external dependencies, but running `npm install` is still recommended to ensure the environment is ready.

## How to Run the Project

### Start the Quiz App

```bash
npm start
```

This executes:

```bash
node index.js
```

### Run Tests

```bash
npm test
```

This executes:

```bash
node --test
```

## Application Flow

1. **Launch the app**
   - `index.js` starts the CLI application.

2. **Show welcome banner**
   - The user is greeted with a formatted introduction.

3. **Choose a category**
   - The app reads quiz topics from `data/questions.json`.

4. **Choose question count**
   - The user selects how many questions to attempt.

5. **Run quiz session**
   - `src/quiz.js` handles question display, answer collection, scoring, and progress updates.

6. **Show results**
   - The quiz displays the final score and summary.

7. **Review incorrect answers**
   - Wrong answers are reviewed with explanations from the JSON data.

8. **Replay or exit**
   - The user may choose to play again.

## Quiz Data Format

The quiz content is stored in `data/questions.json` and follows a category-based structure.

Example shape:

```json
{
  "javascript": {
    "title": "JavaScript Basics",
    "questions": [
      {
        "question": "What does JS stand for?",
        "options": [
          "Java Source",
          "JavaScript",
          "Just Script",
          "Joint Syntax"
        ],
        "answer": "JavaScript",
        "explanation": "JS stands for JavaScript."
      }
    ]
  }
}
```

### Supported Category Fields

Each category typically contains:
- `title` — human-readable category name
- `questions` — array of quiz items

Each question typically contains:
- `question` — the question text
- `options` — multiple-choice answers
- `answer` — the correct answer
- `explanation` — explanation shown after the quiz or on review

## Module Interaction

The application is intentionally split into small modules for clarity:

- `index.js` orchestrates the overall app flow
- `src/input.js` handles all terminal interaction
- `src/colors.js` improves the visual output in the terminal
- `src/quiz.js` runs the quiz session logic
- `data/questions.json` supplies the quiz content

This separation makes the project easy to maintain, extend, and test.

## Extending the Project

You can extend the quiz by:

- adding more categories to `data/questions.json`
- adding more questions to existing categories
- expanding `src/colors.js` with additional styles
- improving `src/quiz.js` with timers, difficulty levels, or streak tracking
- adding automated tests for input and quiz behavior

## Notes

- The app is designed for **interactive terminal use**
- It depends on **Node.js built-in APIs**, not a browser environment
- The JSON file is the main content source, so updating questions does not require changing application logic

## License

No license information was provided in the repository contents.
