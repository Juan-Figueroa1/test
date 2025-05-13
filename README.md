
# Automated Tests DevPortal V2 - Execution Guide

This is an execution guide for the Cypress project. Cypress is an end-to-end testing framework for web applications. In this project, you will find sensitive files in `cypress.config.js`, so it's important to handle these files with care.

## Prerequisites

Before running the Cypress project, make sure you have the following installed on your machine:

- Node.js (version 17 or higher)
- npm (usually comes with Node.js)

## Configuration

Follow the steps below to set up and run the Cypress project:

1. **Clone the Repository**: Download or clone the project repository to your local environment.

```bash
git clone (repository-url)
```

2. **Navigate to the Project Directory**: Open your terminal and navigate to the project's root directory.

```bash
cd (project-directory)
```

3. **Install Dependencies**: Install the necessary dependencies using npm.

```bash
npm install
```

4. **Install Cypress**: Download and install Cypress using npm. (If Cypress is not found after running the first command, please try the second one.)

```bash
npm install cypress --save-dev
```
```bash
npm install cypress@latest --save-dev
```

## Configuration of `cypress.config.js` File

1. In the project's root directory, you will find a file named `cypress.config.js.example`. Make a copy of this file and rename it to `cypress.config.js`. Make sure **not** to include this file in version control as it contains sensitive information.

   ```bash
   cp cypress.config.js.example cypress.config.js
   ```

2. Edit the `cypress.config.js` file and enter specific configurations for your environment, such as application URLs and access credentials. Make sure to protect this information as the `cypress.config.js` file should not be shared publicly.

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

## Alternative OS

If you encounter issues when running the Cypress commands on a Windows device, consider switching to Windows Subsystem for Linux (WSL). WSL allows you to run a Linux distribution alongside your Windows installation, which can help resolve compatibility issues.

### Installing WSL
1. **Open Windows PowerShell or Command Prompt**: Run it in administrator mode by right-clicking and selecting "Run as administrator".

2. **Install WSL**: Enter the following command to enable the necessary features and install the Ubuntu distribution of Linux as the default.

    ```bash
    wsl --install
    ```

3. **Verify the Installation**: After installation, you can verify it by opening PowerShell or Command Prompt and entering:

    ```bash
    wsl --list --verbose
    ```

For more detailed instructions and troubleshooting tips, refer to the official Microsoft documentation:
- [InstallWSL on Windows

## Final Considerations

Make sure to review the official Cypress documentation for additional information on how to write and run tests. Cypress offers a wide range of powerful features for automating your end-to-end tests.

- Cypress Documentation

Always remember to protect your credentials and sensitive information, avoiding accidentally sharing or exposing them publicly.
