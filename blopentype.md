# Basic LuaTeX OpenType Handler Minimal User Guide

As for version 0.0.0 December 2022

Fonts (fonts.ltm and fonts.lts)
==================================

The fontloader uses gates, but only superficially. They won't be
documented here.

To load a given font, you define it in YaX syntax with the `\setfont` command.

```\setfont <command>:<attributes>```

Sets <command> to call the font described in <attributes>; all defaults
to the values of the `metafont` parameter. If `<command>` is `\mainfont`, 
as the name of the main font for the document, the font is called at once; 
any other `\command` requires explicit calls.

You may thing of `\setfont <command>` as similar to DEKTeX's `\font\cmr10 at 12pt` 
or whatever font definition, but now the call is to an array of font attributes.

`name`
The family name of the font; e.g. Palatino Linotype for the main text of
this document.

`size (dimension)`
The size of the font.

`small (dimension)`
The size of the font when \small is called. Can be a relative value by
prefixing it with "-" or "+", in which case it is set relative to ?size.

`verysmall (dimension)`
The size (possibly relative) for \verysmall.

`big (dimension)`
The size (possibly relative) for \big.

`verybig (dimension)`
The size (possibly relative) for \verybig.

`bold (font modifier)`
The modifier used for the bold version of the font, without the leading slash;
!metafont sets it to "Bold".

`italic (font modifier)`
Same as !bold for the italic version; set to "Italic" by !metafont.

`math (true or false)`
If true, math fonts will be created.

`features`
Well, err, font features...

`slant (angle)`
The slant applied to the font to create a fake italic.

`slantsc (angle)`
The slant applied to the font to create fake italic smallcaps; if not
given, defaults to ?slant.

There's actually much more going under the hood, but "font.ptxlua" (the
font loader itself) is a work in progress, and undocumented.

# Font change commands

The same macros as in plain TeX can be used, except they're cumulative,
i.e. "\it\bf" switches to a bold italic.
`<text>` in the specification should be group delimited with braces.

`\it`
Switches to italics.

`\rm`
Switches to roman.

`\bf`
Switches to bold.

`\rg`
Switches to regular weight.

`\sc`
Switches to small capitals.

`\lc`
Switches to lower case (i.e. not small caps).

`\ital <text>`
Typesets <text> in italics.

`\bold <text>`
Typesets <text> in bold.

`\scap <text>`
Typesets <text> in small caps.

`\rom <text>`
Typesets <text> in roman.

`\emph <text>`
Typesets <text> in italics or roman, depending on whether the current
font is roman or italics, respectively.

`\underline <text>`
Underlines <text>. Wow.

`\small`
Switches to small font.

`\verysmall`
Switches to very small font.

`\big`
Switches to big font.

`\verybig`
Got it?

`\normalsize`
Switches to default size.

`\smaller`
Switches to the font smaller than the current one (e.g. \normalsize if
you're currently using \big).

`\bigger`
Same as \smaller, the other way around.

`\color <color><text>`
Typesets <text> with <color>, which should be a triplet "R G B" with
each value between 0 and 1.

# See also

Documentation for [YaX](https://ctan.org/pkg/yax) for the YaX syntax to set up the fonts.

Good luck and happy LuaTeXing,

Luis Rivera

