# cgo-example

Example to illustrate a build problem I'm having:

Suppose `fancylibrary` implements some functionality that I'd like to optionally enable with a build tag, whilst providing a pure-go backup implementation.

This works fine, as long as don't have any .c files in my directory. In which case, when I compile the pure go version, the source files are detected and cause an error.

We can compile just fine when using fancy library:
```
$ go install --tags fancylibrary .
```

But when it is disabled, go complains about the C source files:
```
$ go install  .
can't load package: package github.com/rosshemsley/cgo-example: C source files not allowed when not using cgo or SWIG: hello.c
```