Original code from: https://github.com/gopinav/React-TypeScript-Webpack-Starter

### How use template
```node
npx degit git@github.com:rrudling/react-ts-template.git app
```

### Want to use Tailwind JIT?
**If not:** Delete `tailwind.config.js`.
```bash
cd app
yarn add -D @tailwindcss/jit autoprefixer postcss tailwindcss
yarn add postcss-cli

mkdir src/styles
touch src/styles/output.css
touch src/styles/tailwind.css
echo "@tailwind base;" >> src/styles/tailwind.css
echo "@tailwind components;" >> src/styles/tailwind.css
echo "@tailwind utilities;" >> src/styles/tailwind.css

npx tailwindcss init -p
```
