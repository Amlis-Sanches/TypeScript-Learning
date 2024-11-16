---
tags:
  - ChatGPT
---

To set up TypeScript in VS Code, follow these steps:

### 1. **Install Node.js and npm**
TypeScript requires Node.js to run. Download and install Node.js from [nodejs.org](https://nodejs.org/). It comes with npm (Node Package Manager), which you'll use to install TypeScript.

### 2. **Install TypeScript**
Open a terminal and run:
```bash
npm install -g typescript
```
This installs TypeScript globally on your system. You can verify the installation by running:
```bash
tsc --version
```

### 3. **Install VS Code**
Download and install [Visual Studio Code](https://code.visualstudio.com/).

### 4. **Set Up a Project**
1. Create a new folder for your TypeScript project.
2. Open the folder in VS Code.

### 5. **Initialize a TypeScript Project**
Run this command in the terminal to create a `tsconfig.json` file, which configures the TypeScript compiler:
```bash
tsc --init
```

### 6. **Install Extensions**
In VS Code, go to the Extensions Marketplace (`Ctrl+Shift+X` or `Cmd+Shift+X`) and install these:
- **ESLint**: For linting TypeScript code.
- **Prettier**: For consistent code formatting.
- **TypeScript and JavaScript Grammar**: Enhances TypeScript support.

### 7. **Set Up a Build System**
Add a script to compile TypeScript to JavaScript:
1. In your project folder, run:
   ```bash
   npm init -y
   ```
2. Install TypeScript locally in your project:
   ```bash
   npm install typescript --save-dev
   ```
3. Add a `build` script to your `package.json`:
   ```json
   "scripts": {
     "build": "tsc"
   }
   ```

### 8. **Create Your First TypeScript File**
1. Create a `src` folder in your project directory.
2. Inside `src`, create a file, e.g., `index.ts`.
3. Write some simple TypeScript code, like:
   ```typescript
   let message: string = "Hello, TypeScript!";
   console.log(message);
   ```

### 9. **Compile and Run TypeScript**
1. Compile the TypeScript file to JavaScript:
   ```bash
   npm run build
   ```
   This generates a `dist` folder (or wherever specified in `tsconfig.json`) with the compiled JavaScript.
2. Run the JavaScript using Node.js:
   ```bash
   node dist/index.js
   ```

### 10. **Customize Your VS Code Settings**
To enable better TypeScript development:
1. Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`) and type "Preferences: Open Settings (JSON)".
2. Add:
   ```json
   {
     "editor.formatOnSave": true,
     "files.autoSave": "onFocusChange"
   }
   ```

Let me know if you'd like help with a specific TypeScript example or concept!