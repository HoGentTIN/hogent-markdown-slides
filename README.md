
# README

## Demo

You can see the slides of this repository at https://hogenttin.github.io/hogent-revealmd/ . Play with it to see what it can do!

## Installation

1. Install [nodejs](https://nodejs.org).
2. Install [reveal-md](https://github.com/webpro/reveal-md):

    ```
    npm install -g reveal-md
    ```

## Usage

### Files

Put your markdown files in the root directory and your images in the [img](./img/) folder.

### Creating slides (debugging)

To develop with live reloading:

```
reveal-md <slides.md> --watch
```

### Create static site (html)

To generate a static site:

```
reveal-md --static
```

This will create the `html` folder. You can always delete this directory if you want to.

### Generate PDF

To generate a PDF:

```
reveal-md <slides.md> --print slides.pdf --print-size A4
```

_The resulting PDF isn't very nice though ... :/ ._

### Automatic deployment

This repo autmatically builds the slides and pushes them to https://hogenttin.github.io/hogent-revealmd/ whenever a commit is pushed to the `main` branch. This is done using using [GitHub actions](https://docs.github.com/en/actions). You can find the workflow in the [.github](./.github) folder.

## Configuration

### Theme

The theme used is https://hogenttin.github.io/hogent-revealjs/reveal.js/css/theme/hogent.css from https://github.com/HoGentTIN/hogent-revealjs . Check that repo for the most up-to-date version.

If you want a custom theme, you can change the `theme` option in [reveal-md.json](./reveal-md.json) to e.g. `style.css` and put a file `style.css` in the root folder of the project.

### Landing page

You can change the template `index-template.html` to create a nice landing page for your course. It uses the [Mustache template engine](https://mustache.github.io/).

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

You can add them to [reveal-md.json](./reveal-md.json)

### [reveal.js](https://revealjs.com/) options

You can add them to [reveal.json](./reveal.json)

## Bugs

-   https://github.com/webpro/reveal-md/issues/439
-   https://github.com/webpro/reveal-md/issues/381
-   https://github.com/webpro/reveal-md/issues/389#issuecomment-1105290037
-   https://github.com/yihui/xaringan/issues/75 (why you can't reference CSS from raw GitHub files)

## Links

-   Inspired by https://github.com/HoGentTIN/hogent-revealjs/ .
