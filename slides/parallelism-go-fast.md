##  Parallelism != go fast

![picture of racing](images/parallel.jpeg)

###BAD!

NO, Ricky Bobby!! No!

NOTE:
Parallelism makes it possible to have race conditions in plugins, which you might not notice until deploy time. These are the worst kinds of bugs, and avoiding parallel execution eliminates this entire class of bugs.

On the other hand, Amdahl’s law stops us from gaining much performance through parallelizing. For a simplified example, say our build process takes 16 seconds in total. Let’s say 50% of it can be parallelized, and the rest needs to run in sequence (e.g. CoffeeScript-then-concatenate-then-UglifyJS). If we run this on a 4-core machine, the build would take 8 seconds for the sequential part plus 8 / 4 = 2 seconds for the parallel part, still totaling 10 seconds, less than a 40% performance gain.

For incremental rebuilds, which constitute the hot path that we really care about, caching tends to eliminate most of the parallelizable parts of the build process anyway, so we are left with little to no performance gain.
