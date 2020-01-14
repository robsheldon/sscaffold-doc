If you're coming from [skeleton.css](http://getskeleton.com/), you should find that your column-based layout largely works the way you expect, but forms and typography have changed a bit.

## .container replaced by article and section

skeleton defined a `.container` selector that served as a wrapper for `.column` elements:
```
.container {
    position: relative;
    width: 100%;
    max-width: 960px;
    margin: 0 auto;
    padding: 0 20px;
    box-sizing: border-box;
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


## Narrower body content

Notice above that the `max-width` for what used to be the `.container` element has been changed from 960px to 80rem -- approximately 800px depending on [the display's resolution](../../sections/scaling/index.md).


## Different .column selector

To prevent conflicts with milligram's `.column` rules, the selectors in the 12-column section have been changed to require one of skeleton's other classes on the same element. For example, this won't work:
```
<div class="column">
    <!-- ... -->
</div>
```
But this will:
```
<div class="one column">
    <!-- ... -->
</div>
```


## Tables

Tables regrettably need a block-level wrapper element with a `table-container` class. There's more explanation about this over on the [table gotcha page](../../ysk/tables/index.md).


## Colors and typography

A slightly different default font and color scheme has been selected, not because there was anything wrong with milligram's, but because it seemed appropriate to not directly copy its default style.


## Reporting other differences

If you have encountered a difference not documented here, please [open an issue on sscaffold's github page](https://github.com/robsheldon/sscaffold-css/issues).