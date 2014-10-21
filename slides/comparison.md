##  Comparison

![picture of grunt Gulp](images/brunch_gulp_grunt.jpeg)

NOTE:
Rake::Pipeline is written in Ruby, which is less ubiquitous than Node in front-end land. It tries to do partial rebuilds as well. Yehuda says it’s not heavily maintained anymore, and that he’s betting on Broccoli.

The Rails asset pipeline uses partial rebuilds as well, and uses very different code paths for development mode and production (precompilation) mode, causing people to have unexpected issues when they deploy. More importantly it’s tied to Rails as a backend.
