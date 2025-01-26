
# go

## terms

 - csp = communicating sequential processes (alternative concurrency model to mutexes and semaphores.)

## project layout

 - project layout
   - README.md ⇒ readme
   - Makefile  ⇒ make
   - go.mod    ⇒ go build process
   - go.sum    ⇒ go build process
   - cmd/      ⇒ programs
   - pkg/      ⇒ libraries
   - tests/    ⇒ integration tests
   - ......................
   - build/    ⇒ Dockerfile
   - deploy/   ⇒ K8s files
   - scripts/  ⇒ micellany
   - vendor/   ⇒ modules

## words to live by
 
 - some rules of thumb.
   - clear is better than clever
   - a little copying over a little dependency
   - concurrency is not parallelism
   - channels orchestrate, mutexes serialize
   - don't communicate by sharing memory, share memory by communicating
   - make the zero value useful
   - the bigger the interface the weaker the abstraction
   - errors are values
   - don't just check errors, handle them gracefully


## good sources

 - [Matt KØDVB - Go Class: 41 Building Go Programs](https://youtu.be/rXgUP_BNyaI?t=442)
