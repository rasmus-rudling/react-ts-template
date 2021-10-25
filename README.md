Original code from: https://github.com/gopinav/React-TypeScript-Webpack-Starter

### How use template
```node
npx degit git@github.com:rrudling/react-ts-template.git app
cd app
yarn
```

### Want to use Tailwind JIT?
Links I used for inspiration:
- [Set Up Tailwind JIT In React - The fastest way! 🚀](https://devdojo.com/savio/set-up-tailwind-jit-in-react-the-fastest-way)
- [How to set up tailwindcss with create-react-app + jit feature](https://dev.to/akov/how-to-set-up-tailwindcss-with-create-react-app-jit-feature-1m20?signin=true)

**If not:** Delete `tailwind.config.js` and `postcss.config.js`.
```bash
yarn add -D tailwindcss@latest postcss-cli@8.3.1 autoprefixer@latest concurrently

mkdir src/styles
touch src/styles/output.css
touch src/styles/tailwind.css
echo "@tailwind base;" >> src/styles/tailwind.css
echo "@tailwind components;" >> src/styles/tailwind.css
echo "@tailwind utilities;" >> src/styles/tailwind.css
```

Change the scripts in `package.json` to:
```json
  "scripts": {
    "start": "webpack serve --config webpack/webpack.config.js --env env=dev",
    "build": "webpack --config webpack/webpack.config.js --env env=prod",
    "lint": "eslint --fix \"./src/**/*.{js,jsx,ts,tsx,json}\"",
    "format": "prettier --write \"./src/**/*.{js,jsx,ts,tsx,json,css,scss,md}\"",
    "test": "echo \"Error: no test specified\" && exit 1",
    "watch:css": "postcss -w src/styles/tailwind.css -o src/styles/output.css",
    "dev": "concurrently \"npm run watch:css\" \"npm run start\""
  },
```
