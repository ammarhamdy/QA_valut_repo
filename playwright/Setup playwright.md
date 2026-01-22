

# TypeScript runs on Node so Verify:
```sh
node -v
npm -v
```

# Create project
```sh
mkdir ts-project
cd ts-project
npm init -y
```

# Install TypeScript
```sh
npm install -D typescript
```

# Create config
```sh
npx tsc --init
```

# Open in VS Code
```
code .
```

# Test it works
Create `index.ts`
```ts
const msg: string = 'TypeScript ready';
console.log(msg);
```
Then compile & run:
```sh
npx tsc
node index.js
```

# If this is for **Playwright**, next step is just:
```sh
npm init playwright@latest
```

# Run Example Test
```sh
npx playwright test
```
+ Will run the example test in `tests/example.spec.ts`
+ Creates a **test-results folder** and HTML report

# View report
```sh
npx playwright show-report
```