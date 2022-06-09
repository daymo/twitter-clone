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

## Adding Prisma

```bash
# initialite prima
npx prisma init --datasource-provider sqlite
```

To format on save using Prettier and this rule to your settings.json

```bash
# Add this json to your settings.json in VSCode
"[prisma]": {
    "editor.defaultFormatter": "Prisma.prisma"
}

# Edit your .env file
DATABASE_URL="file:./dev.db"
```

Create a schema for your project and install the prisma client

```bash
# Install the Prisma client which generates the client and types
npm i @prisma/client

# Create the prisma database
npx prisma db push
```

Please note: Use `migrate dev` instead of `db push` in real projects to create a history of your database when you make changes to the db

Seeding the database with test data

```bash
# To transpile TypeScript you ts-node and Node.js types
npm i -D ts-node @types/node

# Seeding the db
npx prisma db seed

# Seeing the data in the browser
npx prisma studio
```

## Developing

If you prefer to use $root as an alias to access the `src` folder from anywhere in the project edit the `svelte-config.js` ...

```bash
+ import path from 'path'
...
kit: {
+	adapter: adapter(),
+   vite: {
+ 	    resolve: {
+ 		    alias: {
+ 			    $root: path.resolve('./src')
+ 		    }
+ 	    }
+   }
```

... and update the `tsconfig.json` so TypeScript knows where the files are located.

```bash
"compilerOptions": {
    ...
+   "baseUrl": ".",
+		"paths": {
+			"$root/*": ["./src/*"]
+	    }
}
```

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
- Prisma
