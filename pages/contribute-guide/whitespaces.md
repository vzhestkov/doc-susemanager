---
title: Whitespaces
keywords: markdown, syntax, formatting
sidebar: frontpage_sidebar
toc: false
permalink: whitespaces.html
---

### Whitespaces

#### Newlines

*Don't* use 2 or more consecutive empty lines, that is,
more than two consecutive newline characters,
except where they must appear literally such as in code blocks.

End files with a newline character, and *don't* leave empty lines at the end of the file.

*Don't* use trailing whitespace unless it has a function such as indicating a line break.

Good:

    - list
    - list

    # Header

Good, code block:

    The markup language X requires you to use triple newlines to separate paragraphs:

        p1


        p2

Bad:

    - list
    - list


    # Header

Rationale: multiple empty lines occupy more vertical screen space,
and do not significantly improve readability.

#### Spaces after sentences

##### Option space-sentence:1 {#option-space-sentence-1}

Use a single space after sentences.

Bad, 2 spaces:

    First sentence.  Second sentence.

Good:

    First sentence. Second sentence.

Rationale: advantages over `space-sentence:2`:

-   easier to edit

-   usually not necessary if you use `wrap:inner-sentence` or `wrap:sentence`

-   `space-sentence:2` gives a false sense of readability
    as it is ignored on the HTML output

-   more popular

Advantages of `space-sentence:2`:

- easier to see where sentences end

##### Option space-sentence:2 {#option-space-sentence-2}

Bad, single space:

    First sentence. Second sentence.

Good:

    First sentence.  Second sentence.
