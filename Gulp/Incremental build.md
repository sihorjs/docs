# Incremental build

1. Use `since` option. Passes files to stream if they have date of last modification later than date of last task run. `since` doesn't read files.

```js
// In gulp options
gulp.task(
  "taskname",
  () => {
    /* body */
  },
  { since: gulp.lastRun("taskname") }
);
```

2. `gulp-newer`. This plugins compares dates of modification source and output files. If output was modified later, source files won't be processed in stream.

3. `gulp-remember`. Caches result of operation.

Creating and deleting cache:

```js
const remember = require("gulp-remember");

gulp.task("styles", () =>
  gulp
    .src("path")
    .pipe(doSomething())
    .pipe(remember("folder"))
);

// Deletes file form cache if it was deleted
gulp
  .watch("path", tasks)
  .on("unlink", file => remember.forget("folder", path.resolve(file)));
```

4. `gulp-cached`. Reads and remembers all input files and prevent proceeding in stream if file has same content.

Deleting cache:

```js
delete cached.caches[cacheName][absolutePath];
```

5. `gulp-cache`. Caches result on disk.
