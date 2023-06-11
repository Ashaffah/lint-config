<h1 align='center'> Setup React Native project with Eslint + Prettier </h1>

1. Create a fresh new React Native project. [https://reactnative.dev/docs/environment-setup?guide=native&platform=ios](https://reactnative.dev/docs/environment-setup?guide=native&platform=ios)

   ```
   npm uninstall -g react-native-cli @react-native-community/cli
   #then
   npx react-native@latest init AwesomeProject
   ```

1. install eslint

   ```
   npm install eslint --save-dev
   #then
   npx eslint --init
   #after you setup init config
   npm install @react-native-community/eslint-config --save-dev
   ```

1. Create a `.eslintrc.json` file in your root directory

   ```
   touch .eslintrc.json
   ```

1. Add the installed plugin to your file in your root directory

   ```
   {
     "env": {
       "browser": true,
       "es2021": true
     },
     "extends": [
       "eslint:recommended",
       "plugin:react/recommended",
       "@react-native-community",
       "prettier"
     ],
     "plugins": ["prettier", "react"],
     "parserOptions": {
       "ecmaVersion": "latest",
       "sourceType": "module"
     },
     "ignorePatterns": [".eslintrc.js", ".SETUP_LINT.md"],
     "rules": {
       "semi": ["error", "never"],
       "comma-dangle": [2, "never"],
       "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }],
       "no-use-before-define": [
         "error",
         { "functions": true, "classes": true, "variables": false }
       ],
       // Remove prettier
       "prettier/prettier": 0
     }
   }

   ```

1. Create a `.prettierrc.json` file in your root directory

   ```
   touch .prettierrc.json
   ```

1. Add the installed plugin to your .prettierrc.json config file

   ```
   {
   "bracketSpacing": true,
   "singleQuote": true,
   "tabWidth": 2,
   "useTabs": false,
   "trailingComma": "none",
   "semi": false
   }

   ```
