hint/transformers >3.0.0 bug
=====================

The below is a minimal reproduction of problems encountered when installing snap with -fdevelopment (i.e. ```cabal install -fdevelopment snap```)

Install instructions/bug demonstration

```shell
$ git clone https://github.com/codygman/hint-transformers-3-bug
Cloning into 'hint-transformers-3-bug'...
remote: Counting objects: 10, done.        
remote: Compressing objects: 100% (6/6), done.        
remote: Total 10 (delta 1), reused 10 (delta 1)        
Unpacking objects: 100% (10/10), done.
Checking connectivity... done.
$ cd hint-transformers-3-bug/
$ cabal sandbox init
Writing a default package environment file to
/home/cody/cabal-debug/hint-transformers-3-bug/cabal.sandbox.config
Creating a new sandbox at
/home/cody/cabal-debug/hint-transformers-3-bug/.cabal-sandbox
$ cabal install -j
Resolving dependencies...
cabal: Could not resolve dependencies:
trying: hint-test-0.1.0.0 (user goal)
trying: hint-0.4.2.1 (dependency of hint-test-0.1.0.0)
next goal: ghc (dependency of hint-0.4.2.1)
rejecting: ghc-7.8.3/installed-4df... (conflict: ghc =>
transformers==0.3.0.0/installed-16a..., hint-test => transformers==0.4.2.0)
Dependency tree exhaustively searched.

Note: when using a sandbox, all packages are required to have consistent
dependencies. Try reinstalling/unregistering the offending packages or
recreating the sandbox.
```
