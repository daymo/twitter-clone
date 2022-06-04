# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm init svelte

# create a new project in my-app
npm init svelte my-app
```

## Manage Node version with NVM

```bash
# check currently used node version
node -v

# switch to newer Node version to satisfy SvelteKit contraints
nvm use 16
```

## Adding TailwindCSS and DaisyUI

```bash
# add TailwindCSS to a new project in the current directory
npx svelte-add@latest tailwindcss

# add env-cmd, daisyui, tailwindcss typography plugin as dev dependencies
npm i -D env-cmd daisyui @tailwindcss/typography
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

## Workflow

Install VSCODE Plugins

- Conventional Commits
