## Setting the base font-size by resolution

An [early reported issue](https://github.com/robsheldon/sscaffold-css/issues/2) prompted an earlier-than-planned change to sscaffold to address potential problems at different display resolutions.

Because sscaffold uses the same `rem`-based approach as milligram and skeleton, these issues could be resolved by changing the `font-size` on the html element from its 62.5% default. The 62.5% default is still relevant today, making `rem`s a useful unit for developers who aren't using preprocessors like scss while still respecting an end-user's accessibility options.

A series of `calc()` functions were originally developed through trial and error, but mnior differences in viewport widths between different browsers at the same screen resolution made the testing process a hairy nightmare. (sscaffold releases are thoroughly tested for regressions and other potential problems with Cross Browser Testing's layout comparison tools.)

There are now three rules defined for low-, medium-, and high-resolution desktop displays. Precautions have been taken to limit the impact on mobile devices, most of which still get the same 62.5% default from milligram and skeleton.

These rules may change significantly in future versions of sscaffold depending on developer and user feedback.
