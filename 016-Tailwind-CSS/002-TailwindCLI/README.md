# Using Tailwind CLI

## 01. Install Node.js (if not already installed)

- Tailwind requires Node.js. If you don’t have it, download and install it from [here](https://nodejs.org/en/download)

- Check if Node.js and npm are installed:

    ```
    node -v
    npm -v
    ```

## 02. Create a New Project (Optional)

- If you're starting a new project, create a folder and navigate into it:

    ```
    mkdir tailwind-project
    cd tailwind-project
    ```
- Initialize a Node.js project
    ```
    npm init -y
    ```

## 03. Install Tailwind via CLI
- Run the following command to install Tailwind CSS:
    ```
    npm install -D tailwindcss
    ```

- Then, generate the Tailwind config file:
    ```
    npx tailwindcss init
    ```

- This creates a `tailwind.config.js` file.

## 04. Open `tailwind.config.js` and specify the paths to your HTML and JavaScript files:

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./*.html", "./src/**/*.js"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```
This tells Tailwind to scan your files for class names. Tailwind scans these files and removes unused styles to keep ```output.css``` small.

## 05. Create a CSS File

- Create a file called `styles.css` in your project folder and add:

    ```
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```

- These three directives in Tailwind CSS are used to inject different layers of styles into your CSS file.

    - `@tailwind base;` → Resets & applies foundational styles.
    - `@tailwind components;` → Loads reusable components.
    - `@tailwind utilities;` → Loads utility classes.

- The order matters. Let's say, if you put `@tailwind utilities;` before `@tailwind components;`, utilities might override components unintentionally.

## 06. Build Tailwind CSS

Run this command to generate the final CSS:

```
npx tailwindcss -i ./styles.css -o ./output.css --watch
```

- ```-i ./styles.css```: Input file

- ```-o ./output.css```: Output file

- ```--watch```: Automatically rebuild on file changes

This command watches for changes and automatically updates ```output.css```.

## 07. Use Tailwind in Your HTML

Link the generated ```output.css``` to the HTML file:
```
<link href="output.css" rel="stylesheet">
```
## 08. Test Tailwind

Create a simple index.html file:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tailwind Test</title>
    <link href="output.css" rel="stylesheet">
</head>
<body class="bg-gray-100 text-center p-10">
    <h1 class="text-3xl font-bold text-blue-600">Hello, Tailwind CSS! 🎨</h1>
    <p class="text-gray-700">Tailwind is working correctly!</p>
</body>
</html>
```

## Folder structure

Here the folder structure looks like this:

```
tailwind-project/
├── index.html
├── src/
│   ├── main.js
├── styles.css
├── output.css (generated)
├── tailwind.config.js
├── package.json
├── node_modules/

```

It may be structured differently as well.