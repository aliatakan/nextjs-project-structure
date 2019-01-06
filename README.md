# Next.js Project Starter Kit

## Purpose Statement
Creating a next.js app is a piece of cake but if you want to add some other development assets into it, there would be some headache for the starters. For example; TypeScript - Next.js integration, importing the css files into the your next.js project or using the Styled-Components. Let me show how to do this step by step.

## Installation
1. First of all, create a project folder and cd into it. I've chosen "next-project-structure" as a folder name

```
mkdir next-project-structure
cd next-project-structure
```

2. Create a new `package.json` file and add some codes in it.

* If you have not a installed node.js, firstly, you need to install it. I use a macOS, therefore;

```
brew install node
```

* Then,

```
npm init -y
```

* Lastly, add some codes in it (be careful !)

```json
{
  "scripts": {
    "dev": "next",
    "build": "next build",
    "start": "next start"
  }
}
```

3. Install `react`, `react-dom` and `next`

```
npm install --save react react-dom next
```
4. Create a folder named `pages`

```
mkdir pages
```

5. TypeScript is a superset of JavaScript and one of the big benefits is to enable IDEs to provide a richer environment for spotting common errors as you type the code. When the team size is big, typing errors are also big! It force you not to write code with typing errors. https://www.typescriptlang.org

* We need to install this package which contains type definitions for Next.js
```
npm install --save-dev @types/next
```

6. `next.config.js`, `tsconfig.json`, `.babelrc`

* Install this plugin which implements babel/preset-typescript with Next.js

```
npm install --save @zeit/next-typescript
```

* Create a next.config.js in your project. By doing this, you can use typescript and css in the next

```js
const withTypescript = require('@zeit/next-typescript')
const withCSS = require('@zeit/next-css')
module.exports = withCSS(withTypescript())
```

* Create a .babelrc in your project
```json
{
  "presets": [
    "next/babel",
    "@zeit/next-typescript/babel"
  ]
}
```

* Create a tsconfig.json in your project
```json
{
  "compilerOptions": {
    "allowJs": true,
    "allowSyntheticDefaultImports": true,
    "jsx": "preserve",
    "lib": ["dom", "es2017"],
    "module": "esnext",
    "moduleResolution": "node",
    "noEmit": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "preserveConstEnums": true,
    "removeComments": false,
    "skipLibCheck": true,
    "sourceMap": true,
    "strict": true,
    "target": "esnext"
  }
}
```

7. Also, install the react and react-dom packages which contain type definitions for React and React-dom

```
npm install --save-dev @types/react
npm install --save-dev @types/react-dom
```

8. Install this package in order to import `.css` files in your Next.js project

```
npm install --save @zeit/next-css
```

9. Simply put, Styled-Components is CSS-in-JS
```
npm install --save styled-components
```

10. Install Babel plugin to add support for server-side rendering, minification of style, and a  nicer debugging experience

```
npm install --save-dev babel-plugin-styled-components
```

* Then, add this codes into the .babelrc

```json
"plugins": [
    [
        "styled-components",
        {
            "ssr": true,
            "displayName": true,
            "preprocess": false
        }
    ]
]
```

11. Add index.tsx into the pages folder which only writes "Hello Mars" on the browser

```
export default () => <h1>Hello Mars !!!</h1>;
```

## Conclusion
That's all. All you need is follow all these steps or clone this repository to start a Next.js project which includes TypeScript, Styled-Components and so forth.