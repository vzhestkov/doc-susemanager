---
title: File Names and Extensions
keywords: markdown, syntax, formatting
sidebar: frontpage_sidebar
toc: false
permalink: file-names-and-extensions.html
---

### File extension

Use `.md`.

Rationale: why not `.mkd` or `.markdown`?

- shorter
- more popular
- does not have important conflicts

### File name

Prefer to base the file name on the top-header level:

- replace upper case letters with lower case
- strip articles `the`, `a`, `an` from the start
- replace punctuation and white space characters by hyphens
- replace consecutive hyphens by a single hyphen
- strip surrounding hyphens

Good:

    file-name.md

Bad, multiple consecutive hyphens:

    file--name.md

Bad, surrounding hyphens:

    -file-name-.md

Rationale: why not underscore or camel case? Hyphens are the most popular URL separator today,
and markdown files are most often used in contexts where:

- there are hyphen separated HTML files in the same project, possibly the same directory as the markdown files.
- filenames will be used directly on URLs. E.g.: GitHub blobs.