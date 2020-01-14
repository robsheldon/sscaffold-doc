A few utility classes have been added to sscaffold, mostly imported from milligram to improve compatibility with existing milligram installations.

## .table-container

This class should be added to an element containing a full-width table due to webkit's lack of support for `max-width` on tables. This issue is further detailed [here](../../ysk/tables/index.md).

## .clearfix

This common utility class, also found in milligram, has been added for improved drop-in compatibility with existing sites.

## .float-left and .float-right

<aside class="warning">
    Deprecation warning: these classes will probably be removed from a future version of sscaffold.
</aside>

These classes have been added from milligram also. Because they do nothing more than add a `float: left` or `float: right` rule to affected elements, it makes more sense for these to be handled in a theme stylesheet or in the site's custom stylesheet.