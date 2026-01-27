
# TS compiler
TSC is itself a command-line application written in TypeScript,4 which means you need NodeJS to run it. Follow the instructions on the official NodeJS website to get NodeJS up and running on your machine.

# NodeJS & NPM
NodeJS comes with NPM, a package manager that you will use to manage your project’s dependencies and orchestrate your build. We’ll start by using it to install TSC and `TSLint` (a linter for TypeScript).

Start by opening your terminal and creating a new folder, then initializing a new NPM project in it:
```sh
# Create a new folder
mkdir chapter-2
cd chapter-2
# Initialize a new NPM project (follow the prompts)
npm init
# Install TSC, TSLint, and type declarations for NodeJS
npm install --save-dev typescript tslint @types/node
```

`tslint`
- **`TSLint` is deprecated** ❌  
    It was officially retired in favor of **`ESLint`** back in 2019.
So while this setup will still _work_, it’s no longer what you’d see in modern TypeScript projects.

If this is **for real projects**, I’d swap TSLint for ESLint:
```sh
npm install --save-dev typescript eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin @types/node
```


# `tsconfig.json`

Every TypeScript project should include a file called `tsconfig.json` in its root directory.

This `tsconfig.json` is where TypeScript projects define things like which files should be compiled, which directory to compile them to, and which version of JavaScript to emit.

Create a new file called `tsconfig.json` in your root folder:
```json
{
"compilerOptions": {
		"lib": ["es2015"],
		"module": "commonjs",
		"outDir": "dist",
		"sourceMap": true,
		"strict": true,
		"target": "es2015"
	},
	"include": [
		"src"
	]
}
```

`tsconfig.json` options:

| Option  | Description                                                                                                                                                                                                                                  |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| include | Which folders should TSC look in to find your TypeScript files?                                                                                                                                                                              |
| lib     | Which APIs should TSC assume exist in the environment you’ll be running your code in? This includes things like ES5’s `Function.prototype.bind`, ES2015’s `Object.assign`, and the DOM’s `document.querySelector`.                           |
| module  | Which module system should TSC compile your code to (`CommonJS`, `SystemJS`, `ES2015`, etc.)?                                                                                                                                                |
| outDir  | Which folder should TSC put your generated JavaScript code in?                                                                                                                                                                               |
| strict  | Be as strict as possible when checking for invalid code. <br>This option enforces that all of your code is properly typed. <br>We’ll be using it for all of the examples in the book, and you should use it for your TypeScript project too. |
| target  | Which JavaScript version should TSC compile your code to (`ES3`, `ES5`, `ES2015`, `ES2016`, etc.)?                                                                                                                                           |

Note that while using a `tsconfig.json` file to configure TSC is handy because it lets us check that configuration into source control, you can set most of TSC’s options from the command line too. 

Run `./node_modules/.bin/tsc --help` for a list of available command-line options.

The project’s folder structure should now look this:
```
chapter-2/
├──node_modules/
├──src/
│ └──index.ts
├──package.json
├──tsconfig.json
└──tslint.json
```
Pop open src/index.ts in your code editor, and enter the following TypeScript code:
```sh
console.log('Hello TypeScript!')
```

Compile and run your TypeScript code:
```sh
# Compile TypeScript with TSC
./node_modules/.bin/tsc
# Run your code with NodeJS
node ./dist/index.js
```


There are a couple of shortcuts you can take to do this faster next time:

Install `ts-node`, and use it to compile and run your TypeScript with a single command.

Use a scaffolding tool like `typescript-node-starter` to quickly generate your folder structure for you
