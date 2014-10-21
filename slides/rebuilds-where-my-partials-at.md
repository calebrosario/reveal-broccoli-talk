##  Rebuilds- where my partials at?

![picture of toy story](images/caching.jpg)

NOTE:
“Partial rebuilds” is the classical approach of Make, as well as the Rails asset pipeline, Rake::Pipeline, and Brunch, but I’ve come to believe that it’s unnecessarily complicated.

Broccoli’s approach is much simpler: Ask each plugin to cache its build output as appropriate. When we rebuild, start with a blank slate, and re-run the entire build process. Plugins will be able to provide most of their output from their caches, which takes near-zero time.

Broccoli started off providing some caching primitives, but it turned out unnecessary to have this in the core API. Now we just make sure that the general architecture doesn’t stand in the way of caching.

For plugins that map files 1:1, like the CoffeeScript compiler, we can use common caching code (provided by the broccoli-filter package), leaving the plugin code looking very simple. Plugins that map files n:1, like Sass, need to be more careful about invalidating their caches, so they need to provide custom caching logic. I assume that we’ll still be able to extract some common caching logic in the future.
