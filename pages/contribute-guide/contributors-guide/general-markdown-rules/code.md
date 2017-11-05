---
title: Code
keywords: markdown, syntax, formatting
sidebar: frontpage_sidebar
toc: false
permalink: code.html
---

### Code

#### Dollar signs in shell code

*Don't* prefix shell code with dollar signs `$`
unless you will be showing the command output on the same code block.

If the goal is to clarify what the language is, do it on the preceding paragraph.

Rationale: harder to copy paste, noisier to read.

Good:

    echo a
    echo a > file

Bad:

    $ echo a
    $ echo a > file

Good, shows output:

    $ echo a
    a
    $ echo a > file

Good, language specified on preceding paragraph:

    Use the following Bash code:

    echo a
    echo a > file

#### What to mark as code

Use code blocks or inline code for:

-   executables. E.g.:

        `gcc` is the best compiler available.

    Differentiate between tool and the name of related projects. E.g.: `gcc` vs GCC.

-   file paths

-   version numbers

-   capitalized explanation of abbreviations:

        xinetd stands for `eXtended Internet daemon`

-   other terms related to computers that you don't want to add to your dictionary

Don't mark as code:

-   names of projects. E.g.: GCC
-   names of libraries. E.g.: libc, glibc