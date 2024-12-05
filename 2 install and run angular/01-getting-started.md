# Getting Started with Angular - Simple Guide for Beginners

## Prerequisites
1. **Node.js Installation**
   - Download Node.js from [nodejs.org](https://nodejs.org)
   - Choose the LTS (Long Term Support) version
   - Run the installer
   
   ```
   +-------------------------+
   |     nodejs.org         |
   +-------------------------+
   |                        |
   | +-------------------+  |
   | | Download Node.js  |  |
   | |      18.x.x LTS  |  |
   | +-------------------+  |
   |                        |
   | +-------------------+  |
   | |    Download      |  |
   | |    16.x.x LTS    |  |
   | +-------------------+  |
   +-------------------------+
   ```

2. **Verify Installation**
   Open Command Prompt and type:
   ```
   node --version
   npm --version
   ```
   ```
   +------------------------+
   |    Command Prompt     |
   +------------------------+
   | > node --version      |
   | v18.17.1             |
   |                      |
   | > npm --version      |
   | 9.6.7               |
   +------------------------+
   ```

## Installing Angular CLI
1. **Install Angular CLI globally**
   ```
   npm install -g @angular/cli
   ```
   ```
   +------------------------+
   |    Command Prompt     |
   +------------------------+
   | > npm install -g @angular/cli
   |                      |
   | [====================]|
   | Installing packages..|
   |                      |
   | + @angular/cli       |
   | added XX packages    |
   +------------------------+
   ```

2. **Verify Angular Installation**
   ```
   ng version
   ```
   ```
   +------------------------+
   |    Command Prompt     |
   +------------------------+
   | > ng version         |
   |     _                |
   |    / \   _ __   __ _|
   |   / △ \ | '_ \ / _` |
   |  / ___ \| | | | (_| |
   | /_/   \_\_| |_|\__, |
   |                |___/ |
   |                      |
   | Angular CLI: 16.2.1  |
   | Node: 18.17.1       |
   +------------------------+
   ```

## Create Your First Angular Project
1. **Create new project**
   ```
   ng new my-first-app
   ```
   ```
   +------------------------+
   |    Command Prompt     |
   +------------------------+
   | > ng new my-first-app |
   |                      |
   | ? Would you like to add Angular routing? (y/N)
   | > Yes                |
   |                      |
   | ? Which stylesheet format would you like to use?
   | > CSS                |
   |   SCSS              |
   |   Sass              |
   |   Less              |
   |                      |
   | Creating project... |
   +------------------------+
   ```

2. **Navigate to project folder**
   ```
   cd my-first-app
   ```

3. **Run the application**
   ```
   ng serve
   ```
   ```
   +------------------------+
   |    Command Prompt     |
   +------------------------+
   | > ng serve           |
   |                      |
   | [====================]|
   | Compiling...         |
   |                      |
   | ✔ Compiled successfully.
   | Server is running on |
   | localhost:4200      |
   +------------------------+
   ```

4. **View your application**
   - Open your browser
   - Go to `http://localhost:4200`
   
   ```
   +--------------------------------+
   |    Chrome Browser             |
   +--------------------------------+
   | http://localhost:4200         |
   +--------------------------------+
   |                               |
   |     Welcome to Angular        |
   |                               |
   | [Angular Logo]                |
   |                               |
   | + New Component               |
   | + Angular Material            |
   | + Add PWA Support            |
   | + Add Dependency             |
   | + Run and Watch Tests        |
   | + Build for Production       |
   |                               |
   +--------------------------------+
   ```

## Project Structure
```
my-first-app/
├── src/
│   ├── app/
│   │   ├── app.component.ts
│   │   ├── app.component.html
│   │   ├── app.component.css
│   │   └── app.module.ts
│   ├── assets/
│   └── index.html
├── node_modules/
├── angular.json
└── package.json
```

## What's Next?
- Start exploring the project structure
- Make simple changes to `src/app/app.component.html`
- Learn about components and modules
- Practice with Angular templates

Remember: This is just the beginning! Take your time to understand each concept before moving forward.
