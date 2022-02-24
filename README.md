# Next.js TypeScript & TailwindCSS boilerplate

## Steps to get here

1. Create Next.js app

    ```
    yarn create next-app --typescript
    ```

2. Install and configure ESLint

    ```
    yarn add --dev eslint
    yarn create @eslint/config
    ```
    
    - In ESLint wizard config
        - Choose to check syntax, problems, and style
        - Choose Javascript modules, React, TypeScript, Browser & Node, JS config
        - Answer questions about style:
            - 4 space indentation
            - Double quote strings
            - Unix line endings
            - No semicolons
    
    - In .eslintrc.js
        - Add plugin `@next/next/recommended`
        - Add "object-curly-spacing" rule (warn, always)
        - Add react version to settings https://github.com/yannickcr/eslint-plugin-react#configuration

    - Remove existing .eslintrc.json

3. Fix template files for linter
    
    - Reindent files from 2 to 4 spaces
    - Change quotes from single to double
    - Add `import React from "react"` to all JSX files
    - Check linting with `eslint .`

4. Install and configure Tailwind
    
    ```
    yarn add tailwindcss postcss autoprefixer @tailwindcss/forms
    yarn run tailwindcss init
    ```
    
    - Remove `styles/Home.module.css` its import in `pages/index.tsx`
    - Replace `styles/globals.css` with Tailwind setup:
        ```
        @tailwind base;
        @tailwind components;
        @tailwind utilities;
        ```
    - Remove `className={...}` from `pages/index.tsx`
    
    - Create `tailwind.config.js` according to https://tailwindcss.com/docs/guides/nextjs
    - Add plugin `@tailwindcss/forms` to `tailwind.config.js`

    - Set Tailwind classNames in `pages/index.tsx` to match original boilerplate
