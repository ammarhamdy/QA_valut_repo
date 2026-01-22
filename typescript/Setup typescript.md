
# Check if Node is installed
```
node -v
npm -v
```

# Initialize a TypeScript Project
```
mkdir ts-demo
cd ts-demo
```
Then init TypeScript Project
```
npm init -y
```
This creates a `package.json`.
Clean **Node + TypeScript projects** config
```
{
  "compilerOptions": {
    "target": "ES2020",             // JS version to compile to
    "module": "commonjs",           // Node.js module system
    "rootDir": "./src",             // your TS source folder
    "outDir": "./dist",             // compiled JS output folder
    "strict": true,                 // enable strict type checking
    "esModuleInterop": true,        // allow import from commonjs modules
    "forceConsistentCasingInFileNames": true,
    "skipLibCheck": true,
    "sourceMap": true               // optional: useful for debugging
  }
}
```



# Install TypeScript
```sh
npm install typescript --save-dev
```
Then check typescript version
```
npx tsc --version
```
Optional (for Node.js types):
```
npm install @types/node --save-dev
```

# Create `tsconfig.json`
This configures your TypeScript compiler:
```sh
npx tsc --init
```
You’ll get a `tsconfig.json` For a basic setup


# Compile & Run
Compile TypeScript → JavaScript:
```
npx tsc
```
This will generate `dist/index.js`. Run it:
```sh
node dist/index.js
```
Instead of compiling every time, you can install **ts-node** to run TS directly:
```sh
npm install ts-node --save-dev
npx ts-node src/index.ts
```

