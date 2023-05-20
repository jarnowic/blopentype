# blopentype
Basic LuaTeX OpenType Manager

# Description

In his terse documentation for `PiTeX`, Paul Isambert lists, among the "mandatory PiTeX" files, the following:

| file name            | Description  |
|-|-|
| fonts.ptx            | Interface for fonts; relies on the next file.    |
| fonts.ptxlua         | The Lua fontloader; should become independant some day. |
| foundry-settings.lua | Default settings for the fontloader.             |

Well: the day has come, and the fontloader has now become `blopentype`: a *Basic LuaTeX OpenType Manager*.

The basic code is copied almost verbatim from Isambert's `PiTeX`, save the adoption of the canonical filename extensions `tex` for *LuaTeX macros*, `lua` for *LuaTeX scripts*, and `blot-sets.lua` for the basic basic settings. 
The required dependencies are Isambert packages [texapi](https://ctan.org/pkg/texapi), [YaX](https://ctan.org/pkg/yax) and [Gates](https://ctan.org/pkg/gates), as stated in `DEPENDS.txt`.

You may find an example of usage in the `blottest.[tex|pdf]` files, and some basic documentation in `blopentype.md`.

# Bugs and caveats

The macros are still barely documented, and massively keep the names of their parent (`PiTeX`) package; that may be fixed some day.

The font database is stored at `$HOME/texmf/luatex/foundry/readable.txt`.
It is not updated automatically after installing new fonts: you have to edit it, or else delete/rename(backup) the database by hand, it and rerun LuaTeX to rebuild it.

The character table for each typeface is stored in the `luatex/foundry` directory as a flat `lua` file; it would be nice to have it compiled as a `luac` file to save some space, some day.

Good luck, and happy LuaTeXing

# Authors 

Version 0.0.1 (C) 2023 Paul Isambert (massively) and Luis Rivera (minor surgeon; or rather: kludger).

LaTeX Project Public License, LPPL Version 1.3c 2008-05-04 or MIT License

May 20, 2023
