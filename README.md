## Prerequisites

This repo is ment to serve as a starter template pre-configured with all the stuff needed to create a base setup from which to build your app on top off!

## Engine Locking

This will ensure that all developers working on this project will use the same Node engine and package manager

- `.nvmrc` - Will tell other users of the project which version of Node is used
- `.npmrc` - Will tell other users of the project which package manager is used

package.json

## Git Setup

By default your Next.js project will already have a repo initialized. You can check what branch you are on with `git status`.

```js
git add .

git commit -m 'project initialization'

git remote add origin git@github.com:{YOUR_GITHUB_USERNAME}/{YOUR_REPOSITORY_NAME}.git

git push -u origin {YOUR_BRANCH_NAME}
```

## Code Formatting and Quality Tools

- [eslint](https://eslint.org/) - For best practices on coding standards
- [prettier](https://prettier.io/) - For automatic formatting of code files

## Git Hooks

Note that from this point on we will be using the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/#summary) standard and specifically the Angular convention [described here](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

We are going to implement a tool called [Husky](https://typicode.github.io/husky/#/)

Husky is a tool for running scripts at different stages of the git process, for example add, commit, push, etc. We would like to be able to set certain conditions, and only allow things like commit and push to succeed if our code meets those conditions, presuming that it indicates our project is of acceptable quality.

- `.husky/pre-commit` - This hook says that in order for our commit to succeed, the `yarn lint` script must first run and succeed.

- `.husky/pre-push` - This hook ensures that we are not allowed to `push` to the remote repository unless our code can successfully `build`.

Lastly we are going to add one more tool. A linter for our commit messages.

To configure it we will be using a set of standard defaults, but I like to include that list explicitly in a `commitlint.config.js` file since I sometimes forget what prefixes are available.

## VS Code Configuration

In the root of the project open the directory called `.vscode` and inside there is a file called `settings.json` - This will be a list of values that override the default settings of your installed VS Code.

## Debugging

Inside of your `.vscode` directory there is also a `launch.json` file - This will set up a convenient environment for debugging our application in case we run into any issues during development.

In addition to this, [cross-env](https://www.npmjs.com/package/cross-env) will be necessary to set environment variables if you have teammates working on different environments (Windows, Linux, Mac, etc)

With that package we can update our our `package.json` `dev` script - This will allow you to log server data in the browser while working in dev mode, making it easier to debug issues.

## Getting Started

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
