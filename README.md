# blotter
Basic LuaTeX OpenType managER

# Description

In his terse documentation for `PiTeX`, Paul Isambert states:

> What is PiTeX? Originally, it was a set of files I loaded with plain TeX
to typeset documentation for my packages. But it's not just a few macros
anymore, but rather a format in progress. The format might never see the
public light, but if it does, its originality (compared to existing
format) will be an organization based on the Gates package: everything
will be highly customizable, not because there are tons of options
(although that can be the case too), but because big operations are
divided into gates, i.e. macros with a handle that you can control without
having to rewrite (nor understand) the big operation you're modifying;
which big operation also keeps its integrity, because removing or adding
something is neatly done. It also means that PiTeX can be changed
piecewise, and made into something that bears little resemblance to the
original code. In other words, there is nothing private, nothing forbidden.
For the moment, only sectionning commands and the output routine, plus
callback management in Lua and \everypar, are written with gates. See
the Gates documentation for further information.

Moreover, while listing the "mandatory PiTeX" files, Isambert enumerates:

| file name            | Description  |
|-|-|
| fonts.ptx            | Interface for fonts; relies on the next file.    |
| fonts.ptxlua         | The Lua fontloader; should become independant  some day. |
| foundry-settings.lua | Default settings for the fontloader.             |

Well: the day has come, and the fontloader has now become `blotter`: *the Basic LuaTeX OpenType managER*.

The basic documentation is copied almost verbatim from Isambert's `PiTeX-doc.txt`, save the adoption of the filename extensions `ltm` for *LuaTeX macros*, and `lts` for *LuaTeX scripts*. 
The required dependencies are Isambert packages [texapi](), [YaX]() and [Gates]().

# Bugs and caveats

The macros are still very scarcely documented; that may be fixed some day.

Good luck, and happy LuaTeXing

# Authors 
Paul Isambert (massively) and Luis Rivera 

December 24, 2022
