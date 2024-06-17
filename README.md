# README

Build slides using markdown, whilst adhering to the principles learned from the [How to avoid death By PowerPoint](https://www.youtube.com/watch?v=Iwpi1Lm6dFo) TEDx Talk.

You can see the slides of this repository as a demo at https://hogenttin.github.io/hogent-revealmd/ . Play with it to see what it can do!

-   [Basic usage](#basic-usage)
    -   [Installation](#installation)
    -   [How do I use this?](#how-do-i-use-this)
    -   [Live preview](#live-preview)
    -   [Create static site (HTML)](#create-static-site-html)
    -   [Generate PDF](#generate-pdf)
-   [Configuration](#configuration)
    -   [Theme](#theme)
    -   [Landing page](#landing-page)
    -   [reveal-md options](#reveal-md-options)
    -   [reveal.js options](#revealjs-options)
    -   [Reveal.js plugins](#revealjs-plugins)
-   [Additional tools](#additional-tools)
    -   [Automatic deployment](#automatic-deployment)
    -   [Formatting](#formatting)
    -   [Linting](#linting)
-   [Bugs](#bugs)
-   [Links](#links)

## Basic usage

### Installation

1. Install [nodejs](https://nodejs.org) .
2. Install [reveal-md](https://github.com/webpro/reveal-md) :

    ```bash
    npm install --global reveal-md
    ```

### How do I use this?

Edit, add or delete put your markdown files in the [docs](./docs/) folder. **That's all to get started!** :rocket:

### Live preview

Reveal-md allows you to start up a live preview, so you can instantly see how your slides look like whilst editing the markdown files.

To develop a slideshow with live reloading:

```bash
reveal-md <slides.md> --watch
```

Or all slideshows:

```bash
reveal-md . --watch
```

### Create static site (HTML)

To generate a static site:

```bash
reveal-md --static
```

This will create the `html` folder. You can always delete this directory if you want to.

_This step is only necessary if you want to host your slides yourself on a webserver. If you use Github actions (see below), this step is not needed: it will be done automatically when you push to the repository._

### Generate PDF

To generate a PDF:

```bash
reveal-md <slides.md> --print slides.pdf --print-size A4
```

_The resulting PDF isn't very nice though at the moment ... :/ ._

---

<details>

<summary>Configuration</summary>

## Configuration

:bulb: **You don't have to change these files or settings** if you want to keep things simple. In that case, just ignore this section.

### Theme

If you want another theme, you can change the `theme` option in [reveal-md.json](./reveal-md.json) to point to another CSS file. You can also use an existing link like https://hogenttin.github.io/hogent-revealjs/reveal.js/css/theme/hogent.css from https://github.com/HoGentTIN/hogent-revealjs .

If you copy or fork this repo, but always want to keep the theme of your slides at any time automatically in sync with this repo, you can ... .

a. Set the `theme` option to the URL https://hogenttin.github.io/hogent-revealmd/_assets/theme.css and delete the local CSS file.

or

b. Change `theme.css` so you import https://hogenttin.github.io/hogent-revealmd/_assets/theme.css and then you can add CSS overrides below:

```css
@import url(https://hogenttin.github.io/hogent-revealmd/_assets/theme.css);

/* Add your overrides here, e.g. ... */

ul {
    color: red;
}
```

### Landing page

You can change the template [index-template.html](./index-template.html) to create a nice landing page for your course. It uses the [Mustache template engine](https://mustache.github.io/) .

### [reveal-md](https://github.com/webpro/reveal-md) options

You can add them to [reveal-md.json](./reveal-md.json) .

### [reveal.js](https://revealjs.com/) options

You can add them to [reveal.json](./reveal.json) .

### Reveal.js plugins

You can add additional functionality using [Reveal.js plugins](https://github.com/hakimel/reveal.js/wiki/Plugins,-Tools-and-Hardware). These are not standard supported in reveal-md, but can be [enabled](https://github.com/webpro/reveal-md/issues/102#issuecomment-692494366). E.g., the [Mermaid](https://github.com/zjffun/reveal.js-mermaid-plugin) plugin for drawing graphs is added in this repo as an example on how to do it.

</details>

---

<details>

<summary>Additional tools</summary>

## Additional tools

:bulb: **You don't need this** if you want to keep things simple. In that case, just ignore this section. Otherwise, it's here if you want an example.

### Automatic deployment

This repo automatically builds the slides and pushes them to https://hogenttin.github.io/hogent-revealmd/ whenever a commit is pushed to the `main` branch. This is done using using [GitHub actions](https://docs.github.com/en/actions) . You can find the workflow in the [.github](./.github) folder.

### Formatting

An [editorconfig](https://editorconfig.org/) config has been added in [.editorconfig](./.editorconfig). This works nicely together with [prettier](https://prettier.io/docs/en/) for which additional config has been added in [.prettierrc.yaml](./.prettierrc.yaml):

```bash
prettier --write "**/*.{md,yml,yaml}"
```

:warning: Use 4 spaces for indentation of nested lists. Otherwise the nesting may not work. This is consistent with the [original MarkDown](https://daringfireball.net/projects/markdown/syntax#list) and the [CommonMark](https://spec.commonmark.org/0.31.2/#lists) specs.

### Linting

A [markdownlint](https://github.com/DavidAnson/markdownlint) config has been added in [.markdownlint-cli2.yaml](./.markdownlint-cli2.yaml):

```bash
markdownlint-cli2 "**/*.md"
```

A [yamllint](https://yamllint.readthedocs.io/en/stable/index.html) config has been added in [.yamllint.yaml](./.yamllint.yaml):

```bash
yamllint .
```

You can also use the [pre-commit](https://pre-commit.com/) hooks in [.pre-commit-config.yaml](./.pre-commit-config.yaml) to automatically check this at every local commit.

</details>
