##  Comparison:Grunt

![picture of Samuel](images/samuel.jpg)


NOTE:
Grunt is the most popular task runner in the Node.js world. The download count from the NPM registry is from far the higher. Grunt built is based on a Gruntfile located at the root of your project. Most of the features require the installation of a specific plugin.

Plugins are based on configuration via a Javascript object. Unless you want to write your own plugin, you mostly write no code logic. The community is very active and you will find a lot of resources about Grunt.

Grunt is a task runner, and it never set out to be a build tool. If you try to (ab)use it as a build tool, you quickly find that because it doesn’t attempt to handle chaining (composition), you end up having to manage temporary directories for intermediate build products yourself, adding a lot of complexity to your Grunt configuration. It also does not support reliable incremental rebuilds, so your rebuilds will tend to be slow and/or unreliable; see section “Fast Rebuilds” above.
