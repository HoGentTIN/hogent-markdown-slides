# README

Build slides using markdown, whilst adhering to the principles learned from the [How to avoid death By PowerPoint](https://www.youtube.com/watch?v=Iwpi1Lm6dFo) TEDx Talk.

## Demo

You can see the slides of this repository at https://hogenttin.github.io/hogent-revealmd/ . Play with it to see what it can do!

## Installation

1. Install [nodejs](https://nodejs.org) .
2. Install [reveal-md](https://github.com/webpro/reveal-md) :

    ```console
    npm install -g reveal-md
    ```

## Basic usage

Edit, add or delete put your markdown files in the root directory and your images in the [img](./img/) folder. That's all!

### Creating slides (debugging)

To develop a slideshow with live reloading:

```console
reveal-md <slides.md> --watch
```

Or all slideshows:

```console
reveal-md . --watch
```

### Create static site (html)

To generate a static site:

```console
reveal-md --static
```

This will create the `html` folder. You can always delete this directory if you want to.

### Generate PDF

To generate a PDF:

```console
reveal-md <slides.md> --print slides.pdf --print-size A4
```

_The resulting PDF isn't very nice though at the moment ... :/ ._

## Configuration

:bulb: **You don't have to change these files or settings** if you want to keep things simple. In that case, just ignore this section.

### Theme

If you want another theme, you can change the `theme` option in [reveal-md.json](./reveal-md.json) to point to another CSS file. You can also use an existing link like https://hogenttin.github.io/hogent-revealjs/reveal.js/css/theme/hogent.css from https://github.com/HoGentTIN/hogent-revealjs .

### Landing page

You can change the template [index-template.html](./index-template.html) to create a nice landing page for your course. It uses the [Mustache template engine](https://mustache.github.io/) .

Possible mustache variables are:

```json
{
    "base": "",
    "themeUrl": "./_assets/./hogent.css",
    "pageTitle": "HOGENT - Slides",
    "files": [
        {
            "filePath": "h0.html",
            "fileName": "h0.html",
            "absPath": "C:\\Users\\martijn\\git\\hogent-revealmd\\h0.html",
            "title": "Hoofdstuk 0: gebruik."
        },
        {
            "filePath": "h1.html",
            "fileName": "h1.html",
            "absPath": "C:\\Users\\martijn\\git\\hogent-revealmd\\h1.html",
            "title": "Hoofdstuk 1: mogelijkheden."
        }
        // ...
    ]
}
```

### [reveal-md](https://github.com/webpro/reveal-md) options

You can add them to [reveal-md.json](./reveal-md.json) .

### [reveal.js](https://revealjs.com/) options

You can add them to [reveal.json](./reveal.json) .

### Reveal.js plugins

You can add additional functionality using [Reveal.js plugins](https://github.com/hakimel/reveal.js/wiki/Plugins,-Tools-and-Hardware). These are not standard supported in reveal-md, but can be [enabled](https://github.com/webpro/reveal-md/issues/102#issuecomment-692494366). E.g., the [Mermaid](https://github.com/zjffun/reveal.js-mermaid-plugin) plugin for drawing graphs is added in this repo as an example on how to do it.

## Additional tools

:bulb: **You don't need this** if you want to keep things simple. In that case, just ignore this section. Otherwise, it's here if you want an example.

### Automatic deployment

This repo automatically builds the slides and pushes them to https://hogenttin.github.io/hogent-revealmd/ whenever a commit is pushed to the `main` branch. This is done using using [GitHub actions](https://docs.github.com/en/actions) . You can find the workflow in the [.github](./.github) folder.

### Formatting

A [prettier](https://prettier.io/docs/en/) config has been added in [.prettierrc.json5](./.prettierrc.json5) .

### Linting

A [markdownlint](https://github.com/DavidAnson/markdownlint) config has been added in [.markdownlint.jsonc](./.markdownlint.jsonc) .

## Bugs

-   https://github.com/webpro/reveal-md/issues/439
-   https://github.com/webpro/reveal-md/issues/381
-   https://github.com/webpro/reveal-md/issues/389#issuecomment-1105290037
-   https://github.com/prettier/prettier/issues/5019
-   https://github.com/yihui/xaringan/issues/75 (why you can't reference CSS from raw GitHub files)

## Links

-   Inspired by https://github.com/HoGentTIN/hogent-revealjs/ .
