---
title: Line Wrapping
keywords: markdown, syntax, formatting
sidebar: frontpage_sidebar
toc: false
permalink: line-wrapping.html
---


### Line wrapping

#### Option wrap:inner-sentence {#option-wrap-inner-sentence}

Try to keep lines under 80 characters by breaking large paragraphs logically at points such as:

-   sentences: after a period `.`, question `?` or exclamation mark `!`

-   [clauses](http://www.oxforddictionaries.com/words/clauses):
    after words like `and`, `which`, `if ... then`, commas `,`

-   large [phrases](http://www.oxforddictionaries.com/words/phrases)

It is acceptable to have a line longer than 80 characters,
but keep in mind that long sentences are less readable
and look worse in tools such as `git diff`.

Set your editor to wrap lines visually for Markdown in case a large line is present.

Good:

    This is a very very very very very very very very very very very very very long not wrapped sentence.
    Second sentence of of the paragraph,
    third sentence of a paragraph
    and the fourth one.

Rationale:

-   Diffs look better, since a change to a clause shows up as a single diff line.

-   Occasional visual wrapping does not significantly reduce the readability of Markdown,
    since the only language feature that can be indented to indicate hierarchy are nested lists.

-   At some point GitHub translated single newlines to line breaks in READMEs,
    and still does so on comments.
    Currently there is no major engine which does it, so it is safe to use newlines.

-   Some tools are not well adapted for long lines, e.g. Vim and `git diff` will not wrap lines by default.
    This can be configured however via `git config --global core.pager 'less -r'` for Git and `set wrap` for Vim.

Downsides:

-   requires considerable writer effort, specially when modifying code.

-   Markdown does not look like the rendered output, in which there are no line breaks.

    Manual line breaking can make the Markdown more readable than the rendered output,
    which is bad because it gives a false sense of readability encouraging less
    readable long paragraphs.

-   Requires users of programming text editors like Vim, which are usually configured to not wrap,
    to toggle visual wrapping on. This can be automated, but
    [EditorConfig gave it WONTFIX](https://github.com/editorconfig/editorconfig/issues/168)

-   Breaks some email systems, which always break a line on a single newline, and  
    make your email  
    look  
    something like this.

#### Option wrap:no {#option-wrap-no}

Don't wrap lines.

Rationale: very easy to edit. But diffs on huge lines are hard to read.

#### Option wrap:space {#option-wrap-space}

Always wrap at the end of the first word that exceeds 80 characters.

Rationale: source code becomes is very readable and text editors support it automatically.
But diffs will look bad, and changing lines will be hard.

#### Option wrap:sentence {#option-wrap-sentence}

Rationale: similar advantages as `wrap:inner-sentence`,
but easier for people to follow since the rule is simple:
break after the period. But may produce long lines with hard to read diffs.

Notable occurrence: [ProGit 2](https://raw.githubusercontent.com/progit/progit2/5c285553c0605342339284981a9bb8a6c4e7c18e/book/01-introduction/1-introduction.asc).
