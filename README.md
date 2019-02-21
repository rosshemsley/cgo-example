# cgo-example

Example to illustrate building a library that has a fancy implementation using cgo, and a backup implementation using pure go.

I found that until I added `// !build fancylibrary` to my C code, I was getting the following error:

```
can't load package: package github.com/rosshemsley/cgo-example: C source files not allowed when not using cgo or SWIG: hello.c
```

Adding the comment fixed the build.