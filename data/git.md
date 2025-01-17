
# git

## glossary

 - blob = binary large object (any binary file, ie. file that is not text).

## structure

```text
.git/                    <-
├── branches             <-
├── COMMIT_EDITMSG       <-
├── config               <-
├── description          <-
├── HEAD                 <-
├── hooks                <-
│   └── xyz.sample       <-
├── index                <-
├── info                 <-
│   └── exclude          <-
├── logs                 <-
│   ├── HEAD             <-
│   └── refs             <-
│       ├── heads        <-
│       │   └── main     <-
│       └── remotes      <-
│           └── origin   <-
│               └── main <-
├── objects              <-
│   ├── xx               <-
│   │   └── 38-digit-hex <-
│   ├── info             <-
│   └── pack             <-
└── refs                 <-
    ├── heads            <-
    │   └── main         <-
    ├── remotes          <-
    │   └── origin       <-
    │       └── main     <-
    └── tags             <-
```

## internals

 - commands 
   - porcelain (82)
     - 44 main commands (add, commit, push, pull, ...)
     - 11 manipulators  (config, reflog, replace, ...)
     - 17 interrogators (blame, fsck, rerere, ...)

 - core data types.
   - objects.
     1. blobs  = raw binary file data.
     2. tree   = directory structure: subdir refs + blob refs.
     3. commit = time + message + parent commit ref + tree ref.
   - others.
     4. tags   = ref to a commit.
       - lightweight = pure pointer.
       - annotated   = meta data: message + author.

## sources

 - [So You Think You Know Git - FOSDEM 2024 by GitButler](https://www.youtube.com/watch?v=aolI_Rz0ZqY)

## further reading

 - [Git Internals - How Git Works](https://www.youtube.com/watch?v=P6jD966jzlk)
 - [Git Internals - Intro Video](https://www.youtube.com/watch?v=fWMKue-WBok&list=PL9lx0DXCC4BNUby5H58y6s2TQVLadV8v7)
 - [Git Internals - Git Objects](https://www.youtube.com/watch?v=MyvyqdQ3OjI)
 - [A tour of Git internals](https://www.youtube.com/watch?v=pfOAxFWNUkQ)
 - [Git Internals | Ep.1 Bits and Booze](https://www.youtube.com/watch?v=JYH5ILv5g1g)
 - [Git Internals by John Britton of Github - CS50 Tech Talk](https://www.youtube.com/watch?v=lG90LZotrpo&list=PLIVFFNmCp144Ki90PUUcSEnMdWxsUbglE)

