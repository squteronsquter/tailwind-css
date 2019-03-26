# How to deploy your new website with Tailwind CSS

==================================================

## Create files and directories

```
cd ~/Sites
mkdir yourProj && cd yourProj
mkdir dist src
touch index.html
```

## Initialize npm

`npm init -y`

## Bring in tailwind css as development package

`npm install tailwindcss --save-dev`

## Make a tailwind config file

`npx tailwind init tailwind.js`

## Make your css file and import tailwind into it

```
mkdir -p src/css
touch src/css/main.css
```

Inside the main.css file:

```
@tailwind preflight;
@tailwind components;
@tailwind utilities;
```

## Compile tailwind css from src to production use -o (output)

`npx tailwind build src/css/main.css -o dist/tailwind.css`
