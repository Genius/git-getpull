git-getpull
===========

Quickly find the GitHub pull request that merged your commit to master.

## Motivation

Commit history is hard to maintain! In an ideal world, `git blame` would provide all of the context that you need to determine why some code was written. Unfortunately, the reality is that no team is perfectly disciplined, and sometimes you're going to run across commits with cryptic or ambiguous messages ("bugfix," anyone?).

When a commit message doesn't provide much context, it's useful to be able to look at the GitHub pull request that merged that commit. Pull requests can contain code review comments, discussion over implementation details, before/after pictures of the UI, and more. Pull requests may also have *many* commits associated with them, which together give a clearer sense of the intended change.

This utility allows you to find out which pull request merged a commit into master (assuming the commit came from a pull request—if it didn't, you're SOL!).

## Installation

(Replace `/usr/local/bin` with a location on your path if `/usr/local/bin` is not on your `$PATH`.)

```shell
$ curl -o /usr/local/bin/git-getpull https://raw.github.com/a-warner/git-getpull/master/git-getpull && chmod +x /usr/local/bin/git-getpull
```

## Usage

```shell
$ git getpull 42a3817c
https://github.com/rails/rails/pull/11195
```

## NB

This isn't a perfect tool: if a commit was made directly to master or a pull request was merged via `git rebase`, it will likely print a random pull request (since the script uses a simple `git log --ancestry-path` command to check for pull requests). Most of the time, however, it "does the right thing."

## LICENSE

Copyright (c) 2013 Rap Genius

MIT License

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
