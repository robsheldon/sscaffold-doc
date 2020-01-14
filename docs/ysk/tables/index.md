## A potential gotcha for tables

Tables must be wrapped by a block-level element with a `table-container` class, like so:

```
<body>
    <main>
        <section>
            <div class="table-container">
                <table>
                    <thead>
                        <!-- ... -->
                    </thead>
                    <tbody>
                        <!-- ... -->
                    </tbody>
                </table>
            </div>
        </section>
    </main>
</body>
```

Tables in milligram are intended to use the full width of their parent element:

```
table {
  border-spacing: 0;
  width: 100%;
}
```

This works okay with the rest of milligram, which sets a `max-width` for the "container" element and centers it on the page:

```
.container {
  margin: 0 auto;
  max-width: 112.0rem;
  padding: 0 2.0rem;
  position: relative;
  width: 100%;
}
```

If a table forces an overflow in this situation, a scrollbar should appear, and the user can still access the full contents of the table.

However, setting a max-width on the container element prevents developers from setting background colors or other design rules for a section that fully reaches both sides of the viewport, unless they include a `.container` element in each `section`, which is a bit messy.

`max-width` can be applied to most block-level elements, with one important exception: tables. In webkit browsers, [tables don't support max-width](https://stackoverflow.com/questions/4019604/chrome-safari-ignoring-max-width-in-table), and setting `display: block` on a table element completely ruins the traditional column-based layout of the table's contents in those browsers.

It makes no sense for tables to be the one exception to `max-width` compatibility, but here we are.

Once webkit adds support for `max-width` on table elements, this page and the related rules in sscaffold will be removed.
