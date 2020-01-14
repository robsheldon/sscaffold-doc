The first section in sscaffold.css is reserved for resets: rules that address assorted browser quirks. Resets are still a necessary evil in modern web development.

# Global and multi-element resets

## box-sizing

milligram sets `box-sizing: inherit` on all elements and pseudo-elements, and `box-sizing: border-box` on `html`. This follows the [box-sizing article on css-tricks](https://css-tricks.com/box-sizing/), so it's done here too.

## prefers-reduced-motion

Andy Bell proposes this media selector in his "[modern reset](https://hankchizljaw.com/wrote/a-modern-css-reset/)" and I think it's a good idea too.

## line-height

normalize.css added a global `line-height` rule to `html` because of inconsistent default line heights in different browsers. There is some [discussion about it](https://github.com/necolas/normalize.css/issues/612) on their issues page. The actual value used here doesn't matter as much as that there's a consistent value for all elements.

## scroll-behavior

While not technically a reset, this adds a nice scroll-down effect anytime a user clicks on an anchor link in the same page. This came from Andy Bell's "modern reset"](https://hankchizljaw.com/wrote/a-modern-css-reset/).

## -webkit-text-size-adjust

Setting this to 100% on the `body` element prevents some potential reflow issues on sites viewed on an iPhone, *but only when the site does not have a `viewport` tag*. According to some discussion on [cssrememdy](https://github.com/mozdevs/cssremedy/issues/13), this may not be needed any longer, but it's still here for compatibility with older projects.

## text-rendering

`optimizeSpeed` is included here from Andy Bell's "modern reset". However, [the article he references](https://marco.org/2012/11/15/text-rendering-optimize-legibility) was from 2012, and the rendering bug it describes may not be relevant to any modern browsers. If someone can do sufficient testing to show that this is no longer needed, I'll remove it.

## zero margin

Default margins are removed from a number of elements. `ul` and `ol` only get this rule applied if they have a class attribute present; the thinking goes that bare list elements should retain more of the browsers' defaults, and list elements being used for navigation or other purposes will have a class attribute and should behave more like simple block-level elements.

# Resets for individual and related elements

## main, details, summary, and template

`display` is explicitly set for these elements in normalize.css to fix some default behavior in some browsers.

## hr

`box-sizing`, `height`, and `overflow` values are all set by normalize.css for this element.

## pre, code, kbd, samp

normalize.css sets the `font-family` and `font-size` values for all of these elements, and milligram sets the `white-space` value. A `display` value has been added to these to explicitly render them as block-level elements so that an exception can be made when they are direct descendants of `p` elements -- and then they become inline elements by default. Because `white-space` is set to `pre` on block-level elements, an `overflow` rule is added to ensure that all content remains accessible to the user.

## ul, ol, dl

List elements that have a class attribute get their `padding` and `list-style-type` values reset as in Andy Bell's "modern reset". This approach assumes that list elements without a class attribute should be styled according to the browser's default, while lists being used for navigational or other purposes will have a class attribute. 

## a

Links get a transparent `background-color` from normalize.css to fix an IE 10 issue, and underlined links get Andy Bell's `text-decoration-skip-ink` value to improve readability slightly.

## abbr

normalize.css sets `border-bottom` and `text-decoration` values for these elements if they contain a title attribute.

## b, strong, sub, sup

These elements inherit all of their rules from normalize.css, with the exception of <b\> and <strong\>, which have had their `font-weight` changed to "bolder" due to poor support for this value in common native fonts. [css-tricks has a brief note about this.](https://css-tricks.com/almanac/properties/f/font-weight/#article-header-id-0)

## img

Rules for the img element are copied from normalize.css, milligram, and Andy Bell's "modern reset". The selector has been changed to `body img`, for extra specificity, to cooperate with the `main section > *` and `main article > *` selectors later in the file.

## th, td

Rules from milligram and Jeremy Thomas' [minireset](https://github.com/jgthms/minireset.css/) have been combined here to give table headers and cells a default left `text-align` unless they have an align attribute added to them.

## Form elements: button, input, select, textarea, optgroup, fieldset...

All of these rules come directly from normalize.css or milligram and include whatever comments were available in those projects. These rules collectively try to improve the consistency of form elements across different browsers.