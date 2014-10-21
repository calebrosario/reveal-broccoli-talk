##  Comparison:Gulp

![picture of gulp with holes](images/gulp_holes.gif)


NOTE:
Let’s go back to pure JS task runners with Gulp. This one works the same way as Grunt (one Gulpfile + plugins) but tend to make things simpler by relying on a code logic based on pipes. The idea is that your code is a list of files that require a serie of operation to be applied. The result of each operation is piped to the next one. Plugins are pre-built operation.

The result? A more flexible code than with Grunt, less code required and a lot of plugins to make your life easier. On the counterpart it doesn’t provide clean configuration file and, for the moment, the community is less active.

With streams, plugins now have to worry about race conditions and deadlocks. Also, in addition to having a notion of streams and paths, we need file attributes like last-modified time and size in our API.
