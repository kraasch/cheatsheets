
# git

## glossary

 - blob = binary large object (any binary file, ie. file that is not text).

## structure

### dot-gitconfig

```gitconfig
[user]                               #
  name  = Name                       #
  email = e@mail.com                 #
[diff]                               #
  tool = vimdiff                     #
[merge]                              #
  tool = meld # or lazygit.          #
[init]                               #
  defaultBranch = master             #
[core]                               #
  editor = vim                       #
[credential]                         #
  helper = cache                     #
[filter "lfs"]                       #
  clean    = git-lfs clean -- %f     #
  smudge   = git-lfs smudge -- %f    #
  process  = git-lfs filter-process  #
  required = true                    #
[alias]                              #
  ad = "add ."                       #
  ca = "commit --amend -m"           #
  ph = "!git push; git push --tags"  #
```

### dot-gitattributes

 - run: `git config diff.exif.textconv exiftool`
 - uses smudge+clean filters
 - e.g. for lfs
   - `apt install git-lfs`
   - `git lfs install`
   - `git lfs track '*.mov'`

```text
*.png diff=exif
```

### dot-gitignore

```text
# a comment
dir/
*txt
```

### dot-git

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

 - commands (145)
   - porcelain (82)
     - 44 main commands (add, commit, push, pull, ...)
     - 11 manipulators  (config, reflog, replace, ...)
     - 17 interrogators (blame, fsck, rerere, ...)
     - 10 interactors   (send-email, p4, svn, ...)
   - plumbing (63)
     - 19 manipulators  (apply, commit-tree, update-ref, ...)
     - 21 interrogators (cat-file, for-each-ref, ...)
     -  5 syncing       (fetch-pack, send-pack, ...)
     - 18 internal      (check-attr, sh-i18n, ...)

 - hooks (28)
   - un-useful (17)
     - git email stuff (4)
     - perforce stuff (4)
     - server stuff (6)
     - ms large repo scaling stuff (3)
   - useful (11)
     - commit stuff (4)
       - `pre-commit`
       - `prepare-commit-msg`
       - `commmit-msg`
       - `post-commit`
     - merge stuff (2)
       - `post-merge`
       - `pre-merge-commit`
     - rewrite stuff (2)
       - `pre-rebase`
       - `post-rewrite`
     - switch/push stuff (3)
       - `post-checkout`
       - `reference-transaction`
       - `pre-push`

 - core data types.
   - objects.
     - blobs  = raw binary file data.
     - tree   = directory structure: subdir refs + blob refs.
     - commit = time + message + parent commit ref + tree ref.
   - others.
     - tags   = ref to a commit.
       - lightweight = pure pointer.
       - annotated   = meta data: message + author.
 - other data types.
   - worktree = extra work directories for parallel branching.

## software

 - [tig](https://github.com/jonas/tig)

## sources

 - [So You Think You Know Git - FOSDEM 2024 by GitButler](https://www.youtube.com/watch?v=aolI_Rz0ZqY)

## further reading

 - [Git Internals - How Git Works](https://www.youtube.com/watch?v=P6jD966jzlk)
 - [Git Internals - Intro Video](https://www.youtube.com/watch?v=fWMKue-WBok&list=PL9lx0DXCC4BNUby5H58y6s2TQVLadV8v7)
 - [Git Internals - Git Objects](https://www.youtube.com/watch?v=MyvyqdQ3OjI)
 - [A tour of Git internals](https://www.youtube.com/watch?v=pfOAxFWNUkQ)
 - [Git Internals | Ep.1 Bits and Booze](https://www.youtube.com/watch?v=JYH5ILv5g1g)
 - [Git Internals by John Britton of Github - CS50 Tech Talk](https://www.youtube.com/watch?v=lG90LZotrpo&list=PLIVFFNmCp144Ki90PUUcSEnMdWxsUbglE)

