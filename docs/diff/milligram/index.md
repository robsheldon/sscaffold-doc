If you're coming from milligram, there are some important differences you should be aware of.

## .container replaced by article and section

milligram defined a `.container` selector that served as a wrapper for `.row` and `.column` elements:
```
.container {
  margin: 0 auto;
  max-width: 112.0rem;
  padding: 0 2.0rem;
  position: relative;
  width: 100%;
}
```

This has been replaced by the following rules in the "theme" section of sscaffold:
```
main article,
main section {
    padding: 7.5rem 1.0rem;
    position: relative;
    width: 100%;
}

main section > *,
main article > * {
    max-width: 80rem;
    margin-left: auto;
    margin-right: auto;
}
```

This means that `section` and `article` elements inside `main` are 100% width, but direct child elements of `section` or `article` are width-constrained and centered. There are two main reasons for this change:

* To stay aligned with this project's goal to encourage semantic html;
* To allow for greater design flexibility

On that second point, milligram's default 112-rem max-width on `.container` elements prevents sites from easily applying background colors, images, or other styles to container elements that stretch fully out to both sides of the viewport. With sscaffold, each `section` of a page can have its own styling while its descendant elements still get laid out in a milligram-like way.

You can find a code example on the [Flebox-Based Columns](../../sections/flexbox/index.md) page.


## Rows need a block-level container

To get the constrained-width, centered-on-the-page effect with milligram-style `row` elements, they must have at least one block-level parent between them and the `section` or `article` ancestor.


## .label-inline replaced by label.inline

The `.label-inline` class selector has been replaced by a simpler `.inline` class selector on `label` and `legend` elements.


## Tables

Tables regrettably need a block-level wrapper element with a `table-container` class. There's more explanation about this over on the [table gotcha page](../../ysk/tables/index.md).


## Colors and typography

A slightly different default font and color scheme has been selected, not because there was anything wrong with milligram's, but because it seemed appropriate to not directly copy its default style.


## Reporting other differences

If you have encountered a difference not documented here, please [open an issue on sscaffold's github page](https://github.com/robsheldon/sscaffold-css/issues).