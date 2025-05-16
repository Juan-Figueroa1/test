
# DevPortal V2 - Cypress Test Execution Guide

This guide provides step-by-step instructions for setting up and running Cypress end-to-end tests for the new version of the HP Developer Portal. Since the project includes sensitive information in the cypress.config.js file, it's important to handle this file with care

## Prerequisites

Before running the Cypress project, ensure the following are installed and configured on your machine:

- [Node.js](https://nodejs.org) (version 17 or higher)
- [npm](https://www.npmjs.com/) (usually comes with Node.js)
- [SSH Public Key](https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key) (see instructions below)

## Configuration of Account

Follow these steps before setting up the Cypress project:

1. **Generate an SSH Public Key**
   
   - Open Windows PowerShell.
      
   - Generate an SSH key (if you don't already have one):
      ```bash
      ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
      ```
   - Press enter to accept the default file location
      
   - To view your public key, either navigate to **C:\Users\YourUsername\\.ssh\id_rsa.pub** or run the following command.
      ```bash
      cat ~/.ssh/id_rsa.pub
      ```
  2. **Add your public key to Acquia**

     Once you've created an account and been invited to join our Acquia team:

     - Click your name in the top-right corner.
     - Go to **Account Settings**.
     - Click on **SSH Keys**.
     - Click **Add SSH Key**.
     - Enter a name for your SSH key name
     - Paste your public key.
     - Click **Add**.

 3. **Verify SSH Access to Acquia**

      To confirm your SSH key is correctly configured and accepted by Acquia, run the following command (replace with your email):

      ```bash
      ssh hpdevportal3.dev@hpdevportal3dev.ssh.prod.acquia-sites.com "drush @hpdevportal3.dev user:login --mail=your_email@example.com"
      ```
      
      If successful, you should see the messagge: **"You are now connected to Acquia Cloud"**

## Cypress Project Setup

Follow these steps to set up the Cypress project:

1. **Clone the Repository**: Download or clone the project repository to your local environment.

   ```bash
   git clone <repository-url>
   ```

2. **Navigate to the Project Directory**: Open your terminal and navigate to the project's root directory.


   ```bash
   cd <project-directory>
   ```

3. **Install Dependencies**: Install the necessary dependencies using npm.

   ```bash
   npm install
   ```

4. **Install Cypress**: Download and install Cypress using npm.
   
   ```bash
   npm install cypress --save-dev
   ```
- If Cypress is not found after running the first command, try the following:
     
   ```bash
   npm install cypress@latest --save-dev
   ```

## Configuration of `cypress.config.js` and `.env` File

1. **cypress.confi.js**
    - In the project's root directory, you will find a file named `cypress.config.js.example`.
    - Make a copy of this file and rename it to `cypress.config.js`.
      ```bash
      cp cypress.config.js.example cypress.config.js
      ```
    - Make sure **not** to include this file in version control as it contains sensitive information.
    - Edit the `cypress.config.js` file and enter specific configurations for your environment, such as application URLs and access credentials.
    - Make sure to protect this information as the `cypress.config.js` file should not be shared publicly.

2. **.env**
   - Request the `.env` file from a QA team member.
   - Place the file in the root directory of the Cypress project
   - Open the `.env` file and update the following line with your email:
      ```bash
      CYPRESS_DRUSH_EMAIL="your_email@example.com"
      ```


## Running Tests

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

## Alternative Environment

If you encounter issues when running the Cypress commands on a Windows device, consider switching to Windows Subsystem for Linux (WSL). WSL allows you to run a Linux distribution alongside your Windows installation, which can help resolve compatibility issues.

1. **Open Windows PowerShell or Command Prompt**: Right-click and select "Run as administrator" to launch it with elevated permissions.

2. **Install WSL**: Enter the following command to enable the necessary features and install the Ubuntu distribution of Linux as the default.

   ```bash
   wsl --install
   ```
3. **Verify the Installation**: After installation, you can verify it by opening PowerShell or Command Prompt and entering:

   ```bash
   wsl --list --verbose
   ```
For more detailed instructions and troubleshooting tips, refer to the official Microsoft documentation:

- [Install WSL on Windows](https://learn.microsoft.com/en-us/windows/wsl/install)

## Final Considerations

Make sure to review the official Cypress documentation for additional information on how to write and run tests. Cypress offers a wide range of powerful features for automating your end-to-end tests.

- [Cypress Documentation](https://docs.cypress.io)

Always remember to protect your credentials and sensitive information, avoiding accidentally sharing or exposing them publicly.
