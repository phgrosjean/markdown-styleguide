# Style Guidelines: Markdown

This document contains formatting standards for creating readable, consistent
files using Markdown and R Markdown. It is adapted from an original document [here](https://github.com/carwin/markdown-styleguide), with links and images adapted from [here](https://github.com/tox2ik/markdown-styleguide).


## Basic conventions for Markdown files

  - Wrap all lines at 80 characters
  - Lines exceeding 80 characters should have, at minimum, three words on
    the following line.
    _(see this list item in raw format for an example.)_
  - Denote **Bold** text using the asterisk format: `**bold text**`.
  - Denote _italic_ text using the underscore format: `_emphasized text_` (but you may have to use single asterisks if formatting applies inside a word).
  - Force a linebreak by ending a line with two spaces, no more.


## Headings

  - Header text must use the `atx-style` with no closing `#` character.
  - Include a space between the `#` and the text of the Header.^[1](#1)

    ```
    # Header 1
    ## Header 2
    ### Header 3
    ```

  - Headers spanning more than 80 characters should be re-evaluated.
  - Headers must be preceded and followed by a newline except at the beginning
    of a file.
  - For readability, add two empty lines before major (level 1 and 2, at least) headers and one after them.


## Horizontal Rules

The convention for horizontal rules in this style guide is to use hyphens (instead of asterisks or underscores). Following another basic convention of the guide, horizontal rules should span 80 characters for readability.

    ```
    --------------------------------------------------------------------------------
    ```


## Lists

  - **List items** must be indented 2 spaces further than their parent, with sublists indented 4 spaces further.
  - Unordered list items should use `-` instead of `*`.

    ```
    This is arbitrary text, an unordered list begins on the next line.
      - list item 1
      - list item 2
          - sub-list item
    ```

  - The first level of list items must not be preceded by a newline.
  - All lists must be followed by newlines.

    ```
    This text precedes a list of things.
      - list item 1
      - list item 2
          1. sub-list item 1
          2. sub-list item 2

      - list item 3
      - list item 4

    This is text of any kind that follows a list.
    ```

  - List item lines exceeding 80 characters should, when wrapped, align
    vertically with the beginning of the preceding line's text.

    ```
      - Large, avian creatures, chocobos roughly act as the equivalent of horses,
        being domesticated for use as mounts...
    ```


## Code

  - **Inline code** must use single backticks and must not have spaces between
    the backtick characters and the code.

    ```
    # Bad
    ` .this-is-wrong `

    # Good
    `.this-is-good`
    ```

  - **Fenced code blocks** must be preceded and followed by a newline.
  - When used inside _list items_, **fenced code blocks** must be indented as if
    they were one level deeper that the list item that contains them.

    ```
      - This list item contains a fenced code block
      - Let's show how it might interact with a list.

          ```
          .code-example {
            property: value;
          }
          ```

    There is a newline above this paragraph because it is both the end of a list
    and because it follows a fenced code block.
    ```


## Tables

Like fenced code blocks, tables in Markdown and R Markdown are provided by Markdown Extra which
seems to be pretty widely implemented.

  - Pipe characters must be preceded and followed by spaces for readability.
  - Table column width should be determined by the longest cell in the column.
  - Always format tables so they are readable in pre-processing.

    ```
    # This is completely unreadable, although it is technically valid.
    table header | other table header
    --- | ---
    table data | other table data
    ```

  - Preceding or trailing pipes are optional. Here is an example using them.

    ```
    # This wastes our precious 80 character limit.
    | table header | other table header |
    | ------------ | ------------------ |
    | table data   | table data         |
    ```

  - Tables must always be preceded and followed by newlines.

### Table example

_This table meets all the criteria:_

```
Group                     | Domain          | First Appearance
------------------------- | --------------- | ----------------
ShinRa                    | Mako Reactors   | FFVII
Moogles                   | MogNet          | FFIII
Vana'diel Chocobo Society | Chocobo Raising | FFXI:TOAU
```

_A handsome table in pre-processed markdown is also handsome when rendered:_

Group                     | Domain          | First Appearance
------------------------- | --------------- | ----------------
ShinRa                    | Mako Reactors   | FFVII
Moogles                   | MogNet          | FFIII
Vana'diel Chocobo Society | Chocobo Raising | FFXI:TOAU


## Links

There are two ways to create links: `[]()` or `<>`. First form:

```
[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org
[link text itself]: http://www.reddit.com
```

[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org
[link text itself]: http://www.reddit.com

Second form uses `<>`, ... or even the just the URL that is automatically detected and interpreted as a link:

``` 
http://www.example.com or <http://www.example.com> and sometimes 
example.com (but not on Github, for example).
```

http://www.example.com or <http://www.example.com> and sometimes 
example.com (but not on Github, for example).


## Images

Images are incorporated in a similar way to links, using `![]()`.

```
Here's a logo (hover to see the title text):

Inline-style: 
![alt text](http://www.sciviews.org/images/site-title.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: http://www.sciviews.org/images/site-title.png "Logo Title Text 2"
```

Here's a logo (hover to see the title text):

Inline-style: 
![alt text](http://www.sciviews.org/images/site-title.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: http://www.sciviews.org/images/site-title.png "Logo Title Text 2"


## Footnotes

  1. This is enforced locally through redcarpet2's configuration:
     `:space_after_headers`.
     <a name="1"><a>

