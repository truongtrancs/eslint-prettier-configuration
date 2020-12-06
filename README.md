# Common eslint-prettier-ts-airbnb configuration for NodeJS

# Installation dependencies

## Eslint + Prettier

```bash
yarn add eslint prettier eslint-plugin-prettier eslint-config-prettier --dev
```

## Eslint/Typescript

```bash
yarn add @typescript-eslint/eslint-plugin @typescript-eslint/parser --dev
```

## Eslint/NodeJS (Optional)

```bash
yarn add eslint-plugin-node eslint-config-node --dev
```

## Eslint/Airbnb (Optional)

```bash
npx install-peerdeps --dev eslint-config-airbnb
```

## Eslint/React (Optional)

```
yarn add eslint-plugin-react --dev
```

add below lines to .eslintrc.json
```javascript
module.exports = {
    parser: "@typescript-eslint/parser", // Specifies the ESLint parser
    parserOptions: {
        ecmaVersion: 2020, // Allows for the parsing of modern ECMAScript features
        sourceType: "module", // Allows for the use of imports

        // --- Start: add below lines if @eslint-plugin-react was installed
        ecmaFeatures: {
            jsx: true // Allows for the parsing of JSX
        }
        settings: {
            react: {
                version: "detect" // Tells eslint-plugin-react to automatically detect the version of React to use
            }
        },
        // --- End: add below lines if @eslint-plugin-react installed

    },
    extends: [
        "plugin:react/recommended", // Uses the recommended rules from @eslint-plugin-react

        "plugin:@typescript-eslint/recommended", // Uses the recommended rules from the @typescript-eslint/eslint-plugin

        "prettier/@typescript-eslint", // Uses eslint-config-prettier to disable ESLint rules from @typescript-eslint/eslint-plugin that would conflict with prettier

        "plugin:prettier/recommended" // Enables eslint-plugin-prettier and eslint-config-prettier. This will display prettier errors as ESLint errors. Make sure this is always the last configuration in the extends array.

    ],
    rules: {
    // Place to specify ESLint rules. Can be used to overwrite rules specified from the extended configs
    // e.g. "@typescript-eslint/explicit-function-return-type": "off",
    }
}
```

# Configuration

> Powered by https://www.robertcooper.me/using-eslint-and-prettier-in-a-typescript-project and https://gist.github.com/bradtraversy/aab26d1e8983d9f8d79be1a9ca894ab4
