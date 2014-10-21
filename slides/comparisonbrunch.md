##  Comparison:Brunch

![picture of Brunch](images/brunch.svg)

NOTE:
Brunch, like Gulp, uses a file-based (not tree-based) in-memory API (see this method signature). Like with Gulp, plugins end up falling back to bypassing the build tool when they need to read more than one file. Brunch also tries to do partial rebuilding rather than caching; see section “Caching, Not Partial Rebuilding” above.
