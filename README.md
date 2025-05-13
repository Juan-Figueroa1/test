# Automated Tests DevPortal V2 - Execution Guide

This is an execution guide for the Cypress project. Cypress is an end-to-end testing framework for web applications. In this project, you will find sensitive files in `cypress.config.js`, so it's important to handle these files with care.

## Prerequisites

Before running the Cypress project, make sure you have the following installed on your machine:

- [Node.js](https://nodejs.org) (version 17 or higher)
- [npm](https://www.npmjs.com/) (usually comes with Node.js)
- [ESLint Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) (for code analysis)
- [EditorConfig Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) (for consistent code formatting)


## Configuration

Follow the steps below to set up and run the Cypress project:

1. Download or clone the project repository to your local environment.
2. Navigate to the project's root directory in the terminal.

## Configuration of `cypress.config.js` File

1. In the project's root directory, you will find a file named `cypress.config.js.example`. Make a copy of this file and rename it to `cypress.config.js`. Make sure **not** to include this file in version control as it contains sensitive information.

   ```bash
   cp cypress.config.js.example cypress.config.js
   ```

2. Edit the `cypress.config.js` file and enter specific configurations for your environment, such as application URLs and access credentials. Make sure to protect this information as the `cypress.config.js` file should not be shared publicly.

## Installing ESLint and EditorConfig Extensions

To enhance code quality and maintain consistent code formatting, the following extensions are required:

- ESLint: Install the ESLint extension for Visual Studio Code. Search for "ESLint" in the Extensions view and click on "Install".
- EditorConfig: Install the EditorConfig extension for Visual Studio Code. Search for "EditorConfig" in the Extensions view and click on "Install".

## Running ESLint

ESLint has been integrated into the project to perform code analysis. Use the following scripts to run ESLint on the `cypress/` directory:

- `eslint`: Run ESLint on the `cypress/` directory.

  ```bash
  npm run eslint
  ```
- `eslint:fix`: Run ESLint on the cypress/ directory and automatically fix fixable issues.

  ```bash
  npm run eslint:fix
  ```
Execute the appropriate script based on your needs in the terminal.

## Running the Tests

This Cypress project provides two scripts to run the tests:

- `cy-gui:proxy`: Opens the Cypress Test Runner with proxy settings enabled, allowing you to run tests in an interactive graphical interface while routing traffic through a proxy.

  ```bash
  npm run cy-gui:proxy
  ```

- `cypress:run`: Executes the tests directly in command-line mode.

  ```bash
  npx cypress run
  ```

Choose the appropriate script based on your needs and execute the corresponding command in the terminal.

## Final Considerations

Make sure to review the official Cypress documentation for additional information on how to write and run tests. Cypress offers a wide range of powerful features for automating your end-to-end tests.

- [Cypress Documentation](https://docs.cypress.io)

Always remember to protect your credentials and sensitive information, avoiding accidentally sharing or exposing them publicly.
