# How to deploy your new website with Tailwind CSS

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

Check the file size of the generated tailwind.css file
Currently it is about 406 KB
Too much for so little code
Let's minimize the code of the css file

## Install Post CSS and other necessary components to reduce and minify css

`npm i -D postcss postcss-cli cssnano @fullhuman/postcss-purgecss`

## We also need a regular dependency to watch changes and compile

`npm i watch`

## Create Post CSS config file

`touch postcss.config.js`

Content of the postcss.config.js file is included

## Add scripts to package.json file (these are included in the package.json file)

```
  "scripts": {
    "build:css": "postcss src/css/main.css -o ./dist/tailwind.css",
    "watch": "watch \"npm run build:css\" ./src"
  },
```

## Run these scripts

`npm run build:css`

and then while developing

`npm run watch`

## Check the file size of the generate tailwind.css file!

For the included example it under 4 KB now!
Almost 400% less then before!

_Happy coding_

**Gray Monk**
