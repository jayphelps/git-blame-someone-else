# git-blame-someone-else

> "I love git-blame-someone-else!!" -Linus Torvalds[^linus]

## Install

```bash
$ git clone https://github.com/jayphelps/git-blame-someone-else.git
$ cd git-blame-someone-else
$ sudo make install
```

## Usage

```bash
$ git blame-someone-else <author> <commit>
```

![ezgif-1396449034](https://cloud.githubusercontent.com/assets/762949/12863650/068e2820-cc2e-11e5-80c5-6ebdb71f51ea.gif)

## Disclaimer:

This changes not only who authored the commit but the listed commiter as well. It also is something I wrote as a joke, so please don't run this against your production repo and complain if this script deletes everything.

[^linus]: Linus Torvalds didn't really approve of this. It's a joke to prove it works.