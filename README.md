# React Setup
Basic Setup for All Kinds of Js/Ts React Projects

## React projects installing commands:

### React.js:
`
npx create-react-app . 

or

npx create-react-app my-app

Airbnb Eslint: npm i eslint-config-airbnb
`

### React.ts:
`
npx create-react-app . --template typescript

or

npx create-react-app my-app --template typescript

and

npx tsc --init

compiling command in Typescript

example: tsc index.ts - Generates an equivalent index.js file

Airbnb Eslint for TS: npm install eslint-config-airbnb-typescript \
            @typescript-eslint/eslint-plugin@^4.29.3 \
            @typescript-eslint/parser@^4.29.3 \
            --save-dev
         

Dev Dependency ts-node : npm i ts-node -D

Pure TS: npm i @typescript-eslint/eslint-plugin @typescript-eslint/parser -D
`

## Create folder .vscode

## Create file settings.json and insert snippet:
`
{
  //Could also use --transpile-only
  "code-runner.executorMap": {
    "TypeScript": "npx ts-node --files --trans"
  }
  "prettier.eslintIntegration": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
`

### Create .eslintrc.js file.

#### Insert this snippet in eslintrc.js file:
`
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: [
    "plugin:react/recommended",
    "airbnb",
    "plugin:import/typescript",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:prettier/recommended",
  ],
  parser: "@typescript-eslint/parser",
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: "module",
  },
  plugins: ["react", "@typescript-eslint"],
  rules: {
    "react/jsx-filename-extension": [
      2,
      { extensions: [".js", ".jsx", ".ts", ".tsx"] },
    ],
    quotes: [2, "double", { avoidEscape: true }],
    "no-use-before-define": "off",
    "@typescript-eslint/no-use-before-define": ["error"],
    "import/extensions": [
      "error",
      "ignorePackages",
      {
        js: "never",
        jsx: "never",
        ts: "never",
        tsx: "never",
      },
    ],
  },
  overrides: [
    {
      files: ["**/*.stories.*"],
      rules: {
        "import/no-anonymous-default-export": "off",
        "react/prop-types": "off",
        "import/no-extraneous-dependencies": "off",
        "react/jsx-props-no-spreading": "off",
      },
    },
  ],
};
`

## Create file .prettierrc.js:
`
module.exports = {
  semi: true,
  trailingComma: "all",
  singleQuote: true,
  printWidth: 80,
  tabWidth: 2,
};
`

## Install prettier dependencies:
`
npm i prettier eslint-config-prettier eslint-plugin-prettier -D

`

## Create .editorconfig file and add this snippet:
`
# EditorConfig is awesome: https://EditorConfig.org

# top-most EditorConfig file
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
end_of_line = lf
`

## Package.json example:
`
{
  "name": "doctor",
  "version": "0.1.0",
  "private": true,
  "homepage": ".",
  "dependencies": {
    "@testing-library/jest-dom": "^5.15.0",
    "@testing-library/react": "^11.2.7",
    "@testing-library/user-event": "^12.8.3",
    "@types/jest": "^26.0.24",
    "@types/node": "^12.20.36",
    "@types/react": "^17.0.34",
    "@types/react-dom": "^17.0.11",
    "axios": "^0.24.0",
    "moment": "^2.29.1",
    "prop-types": "^15.7.2",
    "react": "^17.0.2",
    "react-dom": "^17.0.2",
    "react-router": "^6.0.0",
    "react-router-dom": "^6.0.0",
    "react-scripts": "4.0.3",
    "styled-components": "^5.3.3",
    "typescript": "^4.4.4",
    "web-vitals": "^1.1.2"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "storybook": "start-storybook -p 6006 -s public",
    "build-storybook": "build-storybook -s public"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ],
    "overrides": [
      {
        "files": [
          "**/*.stories.*"
        ],
        "rules": {
          "import/no-anonymous-default-export": "off"
        }
      }
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },
  "devDependencies": {
    "@storybook/addon-actions": "^6.3.12",
    "@storybook/addon-essentials": "^6.3.12",
    "@storybook/addon-links": "^6.3.12",
    "@storybook/node-logger": "^6.3.12",
    "@storybook/preset-create-react-app": "^3.2.0",
    "@storybook/react": "^6.3.12",
    "@typescript-eslint/eslint-plugin": "^4.33.0",
    "@typescript-eslint/parser": "^4.33.0",
    "eslint-config-airbnb": "^18.2.1",
    "eslint-config-airbnb-typescript": "^14.0.2",
    "eslint-config-prettier": "^8.3.0",
    "eslint-plugin-prettier": "^4.0.0",
    "prettier": "^2.4.1"
  }
}
`



