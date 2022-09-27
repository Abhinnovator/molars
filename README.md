<div align="center">
  <h1>🦷 Molars 🦷</h1>
  <strong>A webapp to mold dentures and then export them as 3-D printable .stls</strong>
</div>
<br>
![ezgif com-gif-maker](https://user-images.githubusercontent.com/76423272/192600096-676f37ab-6507-4950-b88e-17b59ef3f2ee.gif)
![ujh5hoov9l8l3svpirgb](https://user-images.githubusercontent.com/76423272/170884713-2b285002-2e25-4446-90c9-6b68427ce5ed.gif)
## 📖 Prerequisites

In order to run the project from a container we need `node>=14`, `npm>=7` and `docker>=20` installed on our development machines or
use one of the listed cloud providers we support:

### Gitpod

> ✅ fully ready [integrated development environment](https://www.gitpod.io/docs/editors)

> ⭕ [VS Code settings sync is not ideal](https://github.com/gitpod-io/gitpod/issues/3733)

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/open-sauced/open-sauced)

[Gitpod](https://www.gitpod.io) is mostly free but has [extensive documentation](https://www.gitpod.io/docs/develop) for all its contributing features.

For [Vite](https://vitejs.dev) to work with Gitpod we need to use [a custom Dockerfile](https://www.gitpod.io/docs/config-docker) that lives under [.gitpod.Dockerfile](./.gitpod.Dockerfile).

Open Sauced comes with a pre-defined [.gitpod.yml](./.gitpod.yml) that should work out of the box in multiple [contribution scenarios](https://www.gitpod.io/docs/references/gitpod-yml).

### Replit

> ✅ fully ready [integrated development environment](https://replit.com/site/ide)

> ⭕ [modified contribution workflows](https://docs.replit.com/tutorials/06-github-and-run-button)

[![Open in Replit](https://repl.it/badge/github/open-sauced/open-sauced)](https://repl.it/github/open-sauced/open-sauced)

[Replit](https://replit.com/) is an old service that recently supported [NixOS](https://nixos.org/guides/nix-pills/enter-environment.html), enabling full customisation of the runner and project.

Open Sauced is configured with a shell environment supporting node@16 and npm@8. The build environment script lives in [shell.nix](./shell.nix) and the [repl config](https://docs.replit.com/programming-ide/configuring-repl) lives in [.replit](./replit).

### Codesandbox

> ✅ can be used as editor replacement
>
> ✅ supports deployment preview

> ⭕ [enforces custom package manager for stability](https://codesandbox.io/docs/configuration#sandbox-configuration)
>
> ⭕ low resources [free tier limitations](https://codesandbox.io/docs/faq#are-there-any-limitations-with-sandboxes)

[![Open in CodeSandbox](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/github/open-sauced/open-sauced?fontsize=14&hidenavigation=1&theme=dark&previewwindow=console&runonclick=1)

### Stackblitz

> ✅ can be used as editor replacement
>
> ✅ supports deployment preview

> ⭕ [enforces custom package manager for stability](https://developer.stackblitz.com/docs/platform/turbo/)
>
> ⭕ limited documentation on [container limitations](https://developer.stackblitz.com/docs/platform/project-config)

[![Open in Stackblitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/open-sauced/open-sauced)

### Glitch

> ✅ can be used as editor replacement

> ✅ supports deployment preview

> ⭕ [enforces custom package manager for stability](https://help.glitch.com/kb/article/59-can-i-change-the-version-of-node-js-my-project-uses/)
>
> ⭕ does not support stacked hot module reload
>
> ⭕ severely low resources [free tier limitations](https://help.glitch.com/kb/article/17-what-are-the-technical-restrictions-for-glitch-projects/)

[![Remix on Glitch](./src/icons/remix-button.svg)](https://glitch.com/edit/#!/import/github/open-sauced/open-sauced)

<img align="right" src="https://i.ibb.co/CJfW18H/ship.gif" width="200"/>

## 🖥️ Local development

To install the application:

```shell
npm ci
```

To start a local copy of the app on port `3000`:

```shell
npm start
```

### 🧪 Test

For running the test suite, use the following command. Since the tests run in watch mode by default, some users may encounter errors about too many files being open. In this case, it may be beneficial to [install watchman](https://facebook.github.io/watchman/docs/install.html).

```shell
npm test
```

You can request a coverage report by running the following command:

```shell
npm run test:coverage
```

### 📦 Docker builds

A development preview can also be run from docker:

```shell
docker build -t open-sauced-dev .
docker run -p 8080:80 open-sauced-dev
```

Alternatively you can pull the production container and skip all builds: 

```shell
docker run -dit -p 8080:80 ghcr.io/open-sauced/open-sauced
```

### 🎨 Code linting

To check the code and styles quality, use the following command:

```shell
npm run lint
```

This will also display during development, but not break on errors.

To fix the linting errors, use the following command:

```shell
npm run format
```

### 🚀 Production deployment

A production deployment is a complete build of the project, including the build of the static assets.

```shell
npm run build
```

You can analyze the build by running the following command:

```shell
npm run build:analyze
```

### 🎭 Offline asset optimization

We also have a script for updating `.svg` files used in the project, you only need to run this if you add new assets:

```shell
npm run build:svgo
```

And one for `.png` and `.jpg` files:

```shell
npm run build:squoosh
```

### 🚧 Development debugging

Thanks to [antfu/vite-plugin-inpesct](https://github.com/antfu/vite-plugin-inspect) we can always inspect the bundles in development by navigating to [localhost:3000/__inspect/](http://localhost:3000/__inspect/) in your browser.

### 📙 Storybook

Storybook is being leveraged to mock out visual React components. The latest version of the design system can be found at this [URL](https://sauced-components.netlify.app/).

```shell
npm run storybook
```

![storybook example screenshot](https://user-images.githubusercontent.com/5713670/68147486-0cd14600-ff32-11e9-8cc0-fd91f4171b87.png)

### 🔑 Authentication

Authentication is handled through [OneGraph's AuthGuardian](https://www.onegraph.com/docs/auth_guardian.html) service.

### 💾 Database

This project uses GitHub as a database. When you login, you will be presented with a button to create a goals repository. That repository template lives at [open-sauced/goals-template](https://github.com/open-sauced/goals-template).

### 💨 Service Worker

This project uses the sw-precache to kickstart an offline cache. The offline cache only registers in production. If service needs to be manually removed make an **unregister** call from the registerServiceWorker.js import.

### 🌙 Dark Mode

This project supports "dark mode" styling, and by default it will follow the color preference on your device. It also allows for overriding this using buttons at the top right of the screen, which will persist the preference to local storage on your device. More info about color preference web API's can be found here: [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)

### 📝 Markdown Support

This project leverages [Remirror](https://remirror.io/) for a delightful experience in documenting your Open Source goals. The editor supports markdown features including heading levels, bulleted lists, text formatting, code snippets, and emojis!

## 🤝 Contributing

We encourage you to contribute to Open Sauced! Please check out the [Contributing guide](https://docs.opensauced.pizza/contributing/introduction-to-contributing/) for guidelines about how to proceed.

We have a commit utility called [@open-sauced/conventional-commit](https://github.com/open-sauced/conventional-commit) that helps you write your commits in a way that is easy to understand and process by others.

It is generally integrated as an `npm` script but you can run it with `npx` as well:

```shell
npm run push
```

For any other npm based project or dotnpmrc defaulting to `--yes`:

```shell
npx -y @open-sauced/conventional-commit
```

## 🍕 Community

Got Questions? Join the conversation in our [Discord](https://discord.gg/U2peSNf23P).  
Find Open Sauced videos and release overviews on our [YouTube Channel](https://www.youtube.com/channel/UCklWxKrTti61ZCROE1e5-MQ).

## 🎦 Repository Visualization 

[![Visualization of this repository](./public/diagram.svg)
](./src)

## ⚖️ LICENSE

MIT © [Open Sauced](LICENSE)

