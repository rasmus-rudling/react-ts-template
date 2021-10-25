Original code from: https://github.com/gopinav/React-TypeScript-Webpack-Starter

### How use template
```node
npx degit git@github.com:rrudling/react-ts-template.git app
cd app
yarn
```

### Want to use Tailwind JIT?
**If not:** Delete `tailwind.config.js` and `postcss.config.js`.
```bash
yarn add -D tailwindcss@latest postcss-cli@8.3.1 autoprefixer@latest chokidar-cli concurrently

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
    "start": "react-scripts start",
    "build": "npm run watch:css && react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "watch:css": "postcss src/tailwind.css -o src/index.css",
    "watch": "chokidar \"./src/**/*.js\" -c \"npm run watch:css\"",
    "dev": "concurrently \"npm run watch\" \"npm run start\""
  },
```
