## Support for milligram's flexbox-based columns

milligram's flexbox-based column selectors and rules have their own section in sscaffold and are largely unchanged, with one important exception: milligram's `.container` selector has been replaced by the `main article`, `main section`, `main section > *`, and `main article > *` selectors later in the file, in the "theme" section.

Rows and columns need to be inside any block-level element inside a `section` or `article` element inside the `main` element to prevent conflicts between milligram's `.row` rules and other selectors:

```
<body>
    <main>
        <section>
            <div>
                <div class="row">
                    <div class="column">
                        <!-- ... -->
                    </div>
                </div>
            </div>
        </section>
    </main>
</body>
```

You can see a more complete example on [sscaffold-css.com](https://sscaffold-css.com/), which is also a handcrafted, not-minified demo page.

There is a more complete explanation of this change on the [differences from milligram page](../../diff/milligram/index.md).
