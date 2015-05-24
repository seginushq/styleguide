# Jade and sass Coding Rule

## Background
  This document defines formatting and style rules for Jade and sass. You should keep your code on this.
  This document based on [Google StyleGuide] (https://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml).

## General Style Rules
### Protocol
  Omit the protocol portion (http:, https:) from URLs pointing to images and other media files, style sheets, and scripts unless the respective files are not available over both protocols.
  Omitting the protocol—which makes the URL relative—prevents mixed content issues and results in minor file size savings.

```
a(href='seginus.jp')  Seginus_Site
```
```
.body
  background: url('/image/body.png')
```

### Indentation
  Indent by 2 spaces at a time.
  Do not use tabs or mix tabs and spaces for indentation.
```
doctype html
html
  body
    h1 Hello World!!
```
```
.body
  width: 1200px
```

### Capitalization
  Use only lowercase.
  All code has to be lowercase.
````
img(src='sample.png' alt='sample')
```
```
color: #e5e5e5
```

### Trailing Whitespace
  Remove trailing white spaces.
  Trailing white spaces are unnecessary and can complicate diffs.
```
  p Yes Please
```


## General Meta Rule
### Encoding
  Use UTF-8 (no BOM).
  Make sure your editor uses UTF-8 as character encoding, without a byte order mark.
  Specify the encoding in HTML templates and documents via <meta charset="utf-8">. Do not specify the encoding of style sheets as these assume UTF-8.
  (More on encodings and when and how to specify them can be found in Handling character encodings in HTML and CSS.)

### Comments
  Explain code as needed, where possible.
  Use comments to explain code: What does it cover, what purpose does it serve, why is respective solution used or preferred?
  '//' is visible after compile, '//-' is not visible after compile.
  You should use '//-' to comment on basically. However you need to publish licence or any comments to people.
```
//- TODO; Add links
ul
  li Mail
  li SNS
```

## Jade Style Rule
### Document Type
  You should use HTML5.
```
doctype html
  head
    meta(charset='UTF-8')
```

### Semantics
  Use HTML according to its purpose.
  Use elements (sometimes incorrectly called “tags”) for what they have been created for. For example, use heading elements for headings, p elements for paragraphs, a elements for anchors, etc.
  Using HTML according to its purpose is important for accessibility, reuse, and code efficiency reasons.

### Both ends "="
  Should not use space both ends "=".
```
  a(href="//google.com")google.com
```


## sass Style Rule
### ID and Class Naming
  Use meaningful or generic ID and class names.
  Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element in question, or that are otherwise generic.
  Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change.
  Generic names are simply a fallback for elements that have no particular or no meaning different from their siblings. They are typically needed as “helpers.”
  Using functional or generic names reduces the probability of unnecessary document or template changes.
```
.gallery
.music
.aux
.alt
```

### ID and Class Name Style
  Use ID and class names that are as short as possible but as long as necessary.  Try to convey what an ID or class is about while being as brief as possible.
  Using ID and class names this way contributes to acceptable levels of understandability and code efficiency.
```
.nav

.author
```

### Prefixes
  Prefix selectors with an application-specific prefix (optional).
  In large projects as well as for code that gets embedded in other projects or on external sites use prefixes (as namespaces) for ID and class names. Use short, unique identifiers followed by a dash.
  Using namespaces helps preventing naming conflicts and can make maintenance easier, for example in search and replace operations.
```
.adw-help /* AdWords */
```

### ID and Class Name Delimiters
  Separate words in ID and class names by a hyphen.
  Do not concatenate words and abbreviations in selectors by any characters (including none at all) other than hyphens, in order to improve understanding and scannability.
```
.video-id
```

###Hacks
  Avoid user agent detection as well as CSS “hacks”—try a different approach first.
  It’s tempting to address styling differences over user agent detection or special CSS filters, workarounds, and hacks. Both approaches should be considered last resort in order to achieve and maintain an efficient and manageable code base. Put another way, giving detection and hacks a free pass will hurt projects in the long run as projects tend to take the way of least resistance. That is, allowing and making it easy to use detection and hacks means using detection and hacks more frequently—and more frequently is too frequently.

### Type Selectors
  Avoid qualifying ID and class names with type selectors.
  Unless necessary (for example with helper classes), do not use element names in conjunction with IDs or classes.
  Avoiding unnecessary ancestor selectors is useful for performance reasons.
```
//- Not recommended
ul.example

div.error

//- Recommended
.example

.error
```

### Shorthand Properties
  Use shorthand properties where possible.
  CSS offers a variety of shorthand properties (like font) that should be used whenever possible, even in cases where only one value is explicitly set.
  Using shorthand properties is useful for code efficiency and understandability.
```
//- Not recommended
border-top-style: none
font-family: palatino, georgia, serif
font-size: 100%
line-height: 1.6
padding-bottom: 2em
padding-left: 1em
padding-right: 1em
padding-top: 0
```
```
//- Recommended
border-top: 0
font: 100%/1.6 palatino, georgia, serif
padding: 0 1em 2em
```

### 0 and Units
  Omit unit specification after "0" values.
  Do not use units after 0 values unless they are required.
```
margin: 0
```

### Leading 0s
  Omit leading "0"s in values.
  Do not use put 0s in front of values or lengths between -1 and 1.
```
font-size: .8em
```

### Hexadecimal Notation
  Use 3 character hexadecimal notation where possible.
  For color values that permit it, 3 character hexadecimal notation is shorter and more succinct.
```
color: #ebc
```

## sass Formatting Rules
  You can learn about sass from http://sass-lang.com/guide.
### Declaration Order
  Alphabetize declarations.
  Put declarations in alphabetical order in order to achieve consistent code in a way that is easy to remember and maintain.
  Ignore vendor-specific prefixes for sorting purposes. However, multiple vendor-specific prefixes for a certain CSS property should be kept sorted (e.g. -moz prefix comes before -webkit).
```
background-color: #000
color: #fff
text-align: center
```

###Indent
  Put Indent by 2 spaces at each property.
  If you do not put them, get error.
```
.body
  background-color: #000
  color: #fff
```

###Property Name Stops
  Put Space after ":"
  If you do not put it, get error.

```
//- NG Code 
.body
  background-image:url(image.png)
```
```
//- OK Code
.body
  background-image: url(image.png)
```

### Variable
  Use snake case on naming variable. Between words is '-'.
  You set variable the following naming patern. This is based on BEM.
  [block]-[element]-[modifier]
```
$color-font: #000
$size-window-newtab: 30px
```

###Do not Put Semicolon
  You should not use semicolon.
```
//- NG Code
color: #fff;
```
```
//- OK Code
color: #fff
```

###Selector and Declaration Separation
  Separate selectors and declarations by new lines.
  Always start a new line for each selector and declaration.
```
h1,
h2,
h3
  font-weight: 100
```

### Rule Separation
  Separate rules by new lines.
  Always put a blank line (two line breaks) between rules.

```
.gallery
  width: 300px

.text
  font-weight: 100
```

## sass Meta Rule
### Section Comment
  Group sections by a section comment (optional).
  If possible, group style sheet sections together by using comments. Separate sections with new lines.
```
//- header
.adw-header

//- footer
.adw-footer
```

##Consultation
Google Style Guide
https://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml

## Revision History
Ver 1.0 | 12th May 2015 | Publish Naming Rule
Ver 1.1 | 24th May 2015 | Add "Both ends "="".
