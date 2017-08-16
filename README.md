# Markdown Styleguide

Markdown is a markup language which is, in comparison to XML and HTML,
supposed to be read as is.
Therefore it's very important that it is already formatted
for maximum readability in its source form.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document
are to be interpreted as described in RFC 2119.


## General

Lines MUST not be longer than 80 characters,
except they contain a link which can not be wrapped.

One SHOULD try, however, to shorten the link by stripping unnecessary parts
of the link and using a provided URL shortener.
(E.g. https://youtu.be/0qo78R_yYFA instead of
https://www.youtube.com/watch?v=0qo78R_yYFA)


## Text Style

- `*Italic*` MUST be used instead of `_Italic_`
- `**Bold**` MUST be used instead of `__Bold__`


## Headings

### Code

Headings MUST always be formatted like

```md
# Heading
```

instead of

```md
Heading
======
```


### Spacing

There MUST always be 2 empty newlines above a heading of any level
except 2 headings are directly adjacent,
then there MUST only be 1 empty newline inbetween.

```md
…
Just a test sentence.


# New Heading

## New Subheading

Another test sentence.


## Another Subheading

…
```


## Links and Images

Links and images with long URLs SHOULD be split up into usage and reference.

```md
[GitHub - Create repo]
…
[GitHub - Create repo]: https://help.github.com/articles/create-a-repo/
```

instead of

```md
[GitHub - Create repo](https://help.github.com/articles/create-a-repo/)
```

The reference tag MAY also be shortened to save horizontal space:

```md
[GitHub - How to create a repository][github-repo]
…
[github-repo]: https://help.github.com/articles/create-a-repo/
```


## List

- `-` MUST be used for unordered lists instead of `*`
- `1.` MUST be used for ordered lists instead of `1)`
- There MUST not be an empty newlines between list items
  if the list items span only one line
- All items in an ordered list MUST only be numbered with `1.`.
  This ensures that items can be easily rearranged or copied to other lists
  and that diffs only contain the changed line.
  (They will be rendered as `1. 2. 3.` nevertheless)

```md
1. Apple
1. Banana
1. Pear
```

instead of

```md
1. Apple
2. Banana
3. Pear
```


## Horizontal Rule

- `---` MUST be used instead of `***`
- Not more than 3 dashes SHOULD be used
- There MUST be 1 empty newline above the horizontal rule and 2 below


## Code

Multiline code MUST be written with backticks and it MUST always
be specified which language it is written in (In doubt use `txt`):

````md
```java
// Import some code
import java.util.ArrayList;
import java.security.*;
```
````

and not with indentation

```md
    // Import some code
    import java.util.ArrayList;
    import java.security.*;
```

This ensures that the code is properly sytnax highlighted and a reader
instantly knows in which language the code is written.

Therefore the multiline syntax SHOULD be used preferably
even for single line code.

Calculations (e.g. `5 * 1000 = 5000`) and file paths (e.g. `~/.ssh/config`)
SHOULD also be formatted as inline code.

Shell code should not contain a `$` at the beginning
as it complicates copy and paste.
It's already specified that it is shell code via the `` ```shell `` tag
at the beginning of the code.
