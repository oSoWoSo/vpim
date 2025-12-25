# clitest – Command Line Tester

clitest is a [portable][1] POSIX shell script that performs automatic
testing in Unix command lines.

It's the same concept as in Python's [doctest][2] module: you document
both the commands and their expected output, using the familiar
interactive prompt format, and a specialized tool tests them.

In fact, the doctest [official][3] description can also be used for
clitest:

* The **doctest** module searches for pieces of text that look like
  interactive **Python sessions**, and then executes those **sessions**
  to verify that they work exactly as shown.

* The **clitest** command searches for pieces of text that look like
  interactive **Unix command lines**, and then executes those
  **command lines** to verify that they work exactly as shown.


## Download & install

The full program is just [a single shell script file][4].

Save it, make it executable and move it to a `$PATH` directory:

```bash
curl -sOL https://raw.githubusercontent.com/aureliojargas/clitest/master/clitest
chmod +x clitest
sudo mv clitest /usr/bin
```

Now check if everything is fine:

```
clitest --help
```


## Quick Intro

Save the commands and their expected output in a text file:

♦ [examples/intro.txt][5]

```
$ echo "Hello World"
Hello World
$
```

## CLI Syntax

There's no syntax to learn.

The test files are identical to the good old command line interface
(CLI) you're so familiar

That's it.

Just paste your shell session inside a text file and you have a
ready-to-use test suite.

## Testable Documentation

Clitest can also **extract and run command lines from documentation**,
such as Markdown files. This very `README.md` file you are now reading
is testable with `clitest README.md`. All the command lines inside it
will be run and checked.

No more malfunctioning shell commands in your READMEs, you can have
testable documentation.


It is a technical article, not a boring code-only test file.

# clitest xut

$ echo "Start testing 'xut'"
Start testing 'xut'
$

## 0. xut sync

Test if xut sync repos correctly

```bash
$ ./xut -s                          #=> --egrep ^templates in void-packages:|restricted templates:|Templates in abyss-packages:
```

## 0. - xut update

Test if update works

```bash
$ ./xut -u                          #=> --egrep Checking for updatable packages
$ ./xut -ul                         #=> --egrep ^Debug :|Warning: No updates available
```

# Build tests
