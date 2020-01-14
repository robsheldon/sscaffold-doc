# The complete manual for sscaffold-css

## Quick Start

Documentation is gross, jump ahead to the [quick start](start/using/index.md) if you're in a hurry.

## Overview

sscaffold-css is designed to be an updated alternative for existing [milligram](https://milligram.io/) and [skeleton](http://getskeleton.com/) installations. The project's priorities, in order, are:

* Human-readable css structure
* Consistent layout in modern browsers and devices
* Encourage modern, semantic, structured html
* Compatibility with milligram and skeleton
* Staying true to skeleton and milligram's lightweight origins

sscaffold-css removes milligram's and skeleton's dependency on [normalize.css](https://necolas.github.io/normalize.css/) by directly including many of those reset rules along with suggestions from multiple other sources.

The sscaffold-css file is broken into several distinct sections:

* [Resets](sections/reset/index.md)
* [Layout Scaling](sections/scaling/index.md)
* [Flexbox-Based Columns](sections/flexbox/index.md)
* [12-Column Grid](sections/12column/index.md)
* [Layout](sections/layout/index.md)
* [Utility Classes](sections/utility/index.md)
* [Default Theme](sections/theme/index.md)

Each section has its own documentation.

The emphasis on a human-readable css structure means that some selectors are duplicated throughout the file. The performance impact from this is probably too small to be measured, and far outweighed anyway by many other aspects of modern web development. In exchange we get a file which is much easier to understand and modify.

## Contributing

Questions, suggestions, and pull requests are all welcomed over at the project's [github repository](https://github.com/robsheldon/sscaffold-css).

## Credits

sscaffold-css includes work from:

* [normalize.css](https://necolas.github.io/normalize.css/)
* [milligram.css](https://milligram.io/)
* [skeleton.css](http://getskeleton.com/)
* [minireset.css](https://github.com/jgthms/minireset.css/)
* [Andy Bell's "modern reset"](https://hankchizljaw.com/wrote/a-modern-css-reset/)
* ...and many different authors on [css-tricks.com](https://css-tricks.com/)
