GoVernor
========

```GoVernor``` is A command line wrapper for Golang bundled tool chain.

The Golang bundled tool chain ```go get/build/test...``` comes with a nasty GOPATH environment variable, which must be set before using these tools in order to locate the project and dependent libraries. It's quite bored to set that variable again and again among projects even I get everything in project local directory. So this wrapper script is written to help.

This script would try to guess the best where is the current project root and what value GOPATH should be if it's not set, and then set GOPATH properly before deliver all command line arguements to the real worker command.

## Usage

Put this script on a PATH directory, and use "gov" instead of the bundled Golang command line tool. For example, use

```shell
$ gov get XXX
```

instead of
```shell
$ go get XXX
```

when current working directory(cwd) is in any level beneath a well-formed project directory according to Golang directory structure rules, which typically looks like:

    <project-root>
    ├── bin
    │    ├── <dirs or files>
    │    ├── ...
    ├── pkg
    │    ├── <dirs or files>
    │    ├── ...
    └── src
          ├── <dirs or files>
          ├── ...

Or, make a alias for an interactive shell like this:
```shell
$ alias go=gov
```
