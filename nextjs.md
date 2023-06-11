<h1 align='center'> Setup Next.js 13 project with Eslint + Prettier </h1>

1. Create a fresh new Next js project. [https://nextjs.org/docs/getting-started#automatic-setup](https://nextjs.org/docs/getting-started#automatic-setup)

   ```
   pnpm create next-app --typescript
   ```

1. install prettier

   ```
   pnpm add -D prettier
   ```

1. Use eslint-config-prettier to setup prettier and eslint without conflicts [https://nextjs.org/docs/getting-started#automatic-setup](https://nextjs.org/docs/getting-started#automatic-setup)

   ```
   pnpm add -D eslint-config-prettier
   ```

1. Then, add prettier to your existing ESLint config
   ```
   {
     "extends": ["next", "prettier"]
   }
   ```
1. Install TailwindCSS on your Next.js project [https://tailwindcss.com/docs/guides/nextjs](https://tailwindcss.com/docs/guides/nextjs)

   1. Install Tailwind CSS
      ```
      pnpm add -D tailwindcss postcss autoprefixer
      ```
   1. Run the init command to generate both `tailwind.config.js` and `postcss.config.js`
      ```
      pnpm tailwindcss init -p
      ```
   1. Add the paths to all of your template files in your `tailwind.config.js` file.

      ```
      /** @type {import('tailwindcss').Config} */
      module.exports = {
        content: [
          "./app/**/*.{js,ts,jsx,tsx}",
          "./pages/**/*.{js,ts,jsx,tsx}",
          "./components/**/*.{js,ts,jsx,tsx}",

          // Or if using `src` directory:
          "./src/**/*.{js,ts,jsx,tsx}",
        ],
        theme: {
          extend: {},
        },
        plugins: [],
      }
      ```

   1. Add the @tailwind directives for each Tailwind’s layers to your `globals.css` file.
      ```
      @tailwind base;
      @tailwind components;
      @tailwind utilities;
      ```

1. To automatically sort tailwind classes with prettier [https://github.com/tailwindlabs/prettier-plugin-tailwindcss#installation](https://github.com/tailwindlabs/prettier-plugin-tailwindcss#installation)
   ```
   pnpm add -D prettier-plugin-tailwindcss
   ```
1. Create a `.prettierrc.json` file in your root directory

   ```
   touch .prettierrc.json
   ```

1. Add the installed plugin to your .prettierrc.json config file

   ```
   {
     "trailingComma": "es5",
     "semi": true,
     "tabWidth": 2,
     "singleQuote": true,
     "jsxSingleQuote": true,
     "plugins": ["prettier-plugin-tailwindcss"]

   }
   ```
