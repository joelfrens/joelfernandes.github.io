# Steps to setup tailwindcss in a custom project

### Step 1

Create a new folder. Navigate to the folder in command line

`npm init -y`

This will generate the package.json file

### Step 2

`npm install tailwindcss postcss-cli autoprefixer@9.0.0`

### Step 3

`npm tailwind init`

This will create a tailwind.config.js in the root directory. This is the file that you can use to customise tailwindcss

### Step 4

Create a Postcss config file postcss.config.js in your root directory and specify the postcss plugins that you need to use

```
module.exports = {
	plugins: [
		require('tailwindcss'),
		require('autoprefixer') 
	]
}
```

### Step 5

Create a base tailwind css class in a css directory ex css/tailwind.css. The direcotry path can be anything of your choice

Add the base tailwind css classes in this tailwind.css file

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Step 6

Add a build script to the package.json file

Replace
```
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```

with

```
"scripts": {
    "build": "postcss css/tailwind.css -o build/tailwind.css"
  },
```

The build/tailwind.css file will contain all the built css classes which you can include in your html using the <link> tag


## VS Code Tailwindcss intellisense

https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss
