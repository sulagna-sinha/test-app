# quiz-cli

A simple Node.js command-line quiz app that lets you test your knowledge from the terminal. The app presents questions, accepts answers, scores the quiz, and shows your results at the end.

## Overview

`quiz-cli` is a lightweight terminal-based quiz experience built for Node.js. It is designed to be easy to run locally, easy to extend with new questions, and easy to understand for contributors.

### Features

- Interactive command-line quiz flow
- Multiple quiz questions with score tracking
- Immediate final results after completion
- Simple quiz data format for adding or updating questions
- Suitable for learning, demos, and quick knowledge checks

## Requirements

- Node.js 16+ recommended
- npm or another Node package manager

## Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/sulagna-sinha/test-app.git
   cd test-app
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the quiz app:

   ```bash
   node index.js
   ```

   > If the entry file differs in your branch, run the main CLI file provided by the project.

## Usage

Run the app from your terminal and answer the questions as they appear.

```bash
node index.js
```

During the quiz:

- Read each question carefully
- Enter your answer in the prompt
- Continue until all questions are completed
- Review your final score at the end

## Testing

If the project includes tests, run them with:

```bash
npm test
```

If no automated test suite is configured yet, you can manually verify the app by:

- Running the CLI locally
- Completing a full quiz session
- Checking that scoring and result output behave as expected

## Project Structure

A typical structure for this app looks like:

```text
.
├── README.md
├── package.json
├── index.js
└── data/
    └── quiz.json
```

Your actual structure may vary slightly depending on the branch contents, but the README is intended to document the main CLI entry point and quiz data source.

## Quiz Data Format

Quiz questions are typically stored as a list of objects. Each item should include the question text and the correct answer.

Example format:

```json
[
  {
    "question": "What is the capital of France?",
    "answer": "Paris"
  },
  {
    "question": "Which language runs in the browser?",
    "answer": "JavaScript"
  }
]
```

Recommended fields:

- `question`: The quiz prompt shown to the user
- `answer`: The expected correct answer

You can extend the format with additional fields if needed, such as:

- `options`
- `category`
- `difficulty`

## Extending the App

You can enhance the quiz by adding:

- More questions
- Categories or difficulty levels
- Timers
- Randomized question order
- Per-question feedback
- Persistent high scores

## Contributing

Contributions are welcome. If you update quiz data, improve the CLI flow, or add tests, please keep the README in sync so new users can follow the setup and usage instructions.

## License

Add the appropriate license information for the project here if needed.
