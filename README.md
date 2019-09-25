# Helps

## install:

```bash
npm i -D prettier husky lint-staged
```

## script

```ts
"prettier": "prettier --write src/**/*.{ts,tsx,css,scss,md,json,js,jsx}"
```

## add `.prettierrc`

```json
{
  "arrowParens": "avoid",
  "bracketSpacing": true,
  "htmlWhitespaceSensitivity": "strict",
  "jsxBracketSameLine": false,
  "jsxSingleQuote": true,
  "printWidth": 100,
  "quoteProps": "as-needed",
  "semi": false,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "none",
  "useTabs": true
}
```
## add to `package.json`
```json
"husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.(js|jsx|ts|tsx|json|css|scss|md)": [
      "prettier --write",
      "git add"
    ]
  }
```

# DEBUG IN CHROME
`.vscode/launch.json`
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Chrome",
      "type": "chrome",
      "request": "launch",
      "url": "http://localhost:3000",
      "webRoot": "${workspaceFolder}/src",
      "sourceMapPathOverrides": {
        "webpack:///src/*": "${webRoot}/*"
      }
    }
  ]
}
```
