## Semantic html

An important difference between milligram and skeleton is that sscaffold emphasizes semantic, structured html in place of utility classes. Instead of using a "container" class on divs within a body element, sscaffold looks for `section` or `article` elements inside of a `main` element.

This encourages slightly cleaner, more modern markup.

The [sscaffold-css home page](https://sscaffold-css.com/) is a handcrafted, not-minified demo of many supported elements.

## Features

Some helpful features of sscaffold include:

* A lot of compatibility with both milligram and skeleton
* No external dependencies (milligram and skeleton both require normalize.css)
* Completely restructured css
    - designed for humans
    - with distinct sections
    - and a separate section at the bottom for theming
    - and the theme section is further broken down into typography, layout, and colors
* [Automatic scaling for different display resolutions](../../sections/scaling/index.md)

## Quick start

sscaffold works best with html that looks something like:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
        <!-- ... -->
    </head>
    <body>
        <header>
            <nav>
            </nav>
        </header>
        <main>
            <section>
                <!-- or <article>, followed by content -->
            </section>
            <section>
                <!-- ... -->
            </section>
        </main>
        <footer>
        </footer>
    </body>
</html>
```

## Milligram and Skeleton

sscaffold provides support for much of milligram's and skeleton's css rules, but if you're coming from one of those, you'll probably want to look at [differences from milligram](../../diff/milligram/index.md) or [differences from skeleton](../../diff/skeleton/index.md).