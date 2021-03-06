CHANGE HISTORY
--------------

- v0.8h (2017/10/09)

  * Some bugs crept in in the last update due to some code rearrangement:
      * package version wasn't set;
      * some code was being executed at the wrong time;
      * `\sqrt[]{}` in LuaLaTeX gave incorrect output.
  * The layout of the code is now structured far more sensibly.
  * Remove (long deprecated) `\resetmathfont`; for years it has been a synonym for `\setmathfont`.

- v0.8g (2017/10/02)

  * Better use of scriptstyle sizes in LuaTeX (I think a regression).
  * Fix regression (`\mathbf` etc. not being set automatically) caused by the renaming of a `fontspec` internal command.
  * Minor documentation improvements.
  * (Only relevant for me: I've also disabled the test suite almost entirely to begin a re-write for ‘continuous integration’.)

- v0.8f (2017/08/02)

  * Emergency fix (thanks Bruno) for another bug revealed by `expl3` update.

- v0.8e (2017/07/30)

  * Add `\surd` to access the sqrt symbol.
  * Fix bug exposed by `expl3` update to booleans.
  * Add Deja Vu Math TeX Gyre in list of symbols.
  * Add `\sime` alias for `\simeq` and `\nsimeq` for `\nsime`.
    (For negations it's helpful when they have consistent naming.)

- v0.8d (2017/01/25)

  * `vargreek-shape=TeX` and `vargreek-shape=unicode` package options dropped; for consistency and compatibility, `\phi` and `\epsilon` should and will now behave the same as in `TeX`.
  * On that note, when using control sequences such as `\mbfitsansvarphi` (and so on), there were a few faulty definitions. The new behaviour is to consistenyl define the `varphi` and `varepsilon` ones as those with the "curly" designs.
  * Add `\wideoverbar`, `\widebreve`, `\widecheck`.
  * Add `\mathsection`, `\mathparagraph`.
  * Remove `\mupvarbeta`, `upold(Kk)oppa`, `\up(Ss)tigma`, `\up(Kk)oppa`, `\up(Ss)ampi` — none of these are maths symbols.
  * `!` (`\mathexclam`) changed from `\mathpunct` to `\mathclose` for backwards compatibility with TeX.

- v0.8c (2015/09/24)

  * Add `\over(left/right)harpoon` as "wide" accents.
  * Add RTL mathematics operators `\arabicmaj` and `\arabichad`, which correspond to `U+1EEF0` and `U+1EEF1`, resp.
  * Remove `catchfile` package dependency.
  * Update some internal names to match expl3 standards.

- v0.8b (2015/09/09)

  * Bug fix: Use the "ucharcat" package to simplify some code that caused some headaches with \tl_rescan:nn.

- v0.8a (2015/08/06)

  * Fix bug with \vert, \|, \(l/r)vert, etc., displaying with the wrong characters.

  * Improve documentation to properly reflect changes in v0.8 and fix some broken examples.

  * No longer reset catcodes of : and @ during \setmathfont .

  * Fix remapping of alphabets (needed for Minion Math) in cases such as:

      \setmathfont[range=bfit->it]{MinionMath-Bold.otf}

- v0.8  (2015/07/29)  **Breaking changes in this update!**

  * `\mathrm` (`\mathup`), `\mathit`, `\mathbf`, `\mathsf`, and `\mathtt` revert to their traditional LaTeX meanings; they are set up to match their equivalent text fonts unless specifically set using `\setmathrm` and friends from `fontspec` or the new `\setmathfontface` in `unicode-math`. These commands should be used for *multi*-letter identifiers.

  * New "symbol" commands have been added, `\symrm` (`\symup`), `symit`, ..., to replace the behaviour of the old commands. These should be used for *single*-letter identifiers. See the package documentation for more detail on these and related commands.

  * Package options `mathit=sym`, `mathbf=sym`, etc., reverse the changes above to revert to pre-v0.8 behaviour for `\mathXYZ`. Regardless of package option, `\symXYZ` always maps to symbols and `\mathtextXYZ` is provided for the traditional `\mathXYZ` font switch.

  * New command `\setoperatorfont` to set the font used for commands such as `\sin` and `\cos`. Usage: `\setoperatorfont\mathbf` or any command defined with `\setmathfontface`.

  * Traditional LaTeX `\DeclareMathAlphabet` now works again for legacy font-loading packages.

  * Commands defined to "force" Greek letters with `\upbeta` and `\itbeta`, etc.

  * Assorted bug fixes and minor changes.

- v0.7e (2014/06/30)

  * No longer assume fixltx2e has been loaded.
  * Some ascii math symbols have been renamed with a \math... prefix, such as \mathquestion.
  * Assume latest luaotfload is being used; no need for a separate unicode-math.lua script.
  * Assorted typos and minor bugs.

- v0.7e (2013/05/04)

  * Track luaotfload updates.

- v0.7d (2013/03/16)

  * More expl3 changes missed first time around. (Sorry again.)

- v0.7c (2013/02/25)

  * The Latin Modern math font name changed TWICE. Only caught the first one.
    Sorry for any inconvenience caused.

- v0.7b (2013/02/22)

  * Keep in sync with Latin Modern Math font name change.
  * Keep in sync with expl3 changes.

- v0.7a (2012/07/28)

  * Keep in sync with expl3 changes.

- v0.7 (2012/05/30): The TeX Live 2012 release.

  * Most changes (and all significant ones) in this release thanks to Khaled
    Hosny, who is now credited as an author of the package.
  * Many improvements for XeTeX support to take advantage of the new engine
    (v0.9998) in TL2012.
      * As a result, `\resetmathfont` is no longer required.
  * Improve `\not` to use pre-combined glyphs where possible.
  * LM Math is loaded by default.
  * Support bottom accents.
      * And add `\wideutilde`.
  * The ‘symbols’ document is somewhat better organised and contains
    information on whether a symbol is defined in plain TeX or amssymb.
  * Various other minor fixes and additions:
      * `\underleftrightarrow` added for fonts that support it.
      * Don’t overwrite mathtool’s `\overbracket` and `\underbracket`.
      * Bug in `[range=...]` parsing fixed.
      * Add `\longdivision`.
      * Add `\lgroup` and `\rgroup`.
      * Fix ‘moustache’ delimiters.
      * `\openbox` renamed to `\mathvisiblespace`, since it is already defined
        in amsthm as an empty box.

- v0.6a (2011/09/19)

  * Always a bug that slips through the cracks! Fixes `\left.` and `\right.`
  * Add experimental package option `warnings-off=...` which allows warnings
    to be suppressed on an individual basis.

- v0.6 (2011/09/18)

  * Keep in sync with fontspec internals
    (sorry for the small delay where things were broken)
  * Keep in sync with expl3 deprecated functions
  * Math versions (finally) implemented; can now change maths fonts
    mid-document without reinitialising everything
    (thanks to Ulrike Fischer and Ulrik Vieth)
  * Symbols file `unimath-symbols.pdf` now uses maths versions to compare
    all of the OpenType maths fonts I currently have access to
  * Over- and under- braces, brackets, and parentheses now work in XeTeX
    (thanks to Claudio Beccari)
  * Many internal changes, including a re-write of the `range` feature;
    it should now be faster and more robust
  * Tentative programmer's interface for querying the current math style:
    `\l_um_mathstyle_tl`.
  * Remove (outdated) interaction with beamer; you must specify
    `professionalfonts` manually for now
  * Quieten the console output when loading maths fonts with incomplete maths
    style coverage
  * Synonym added: `\lnot` -> `\neg`
  * Two added Unicode symbols (names tentative): `\blanksymbol` and `\openbox`
    (thanks to Apostolos Syropoulos)
  * Fixed literal sub-/super-script input.

- v0.5e (2011/07/31)

  * Fix forward compatibility clash with deprecated expl3 functions (sorry)
  * Command names are now `\protected`; this makes them safe to use in moving
    arguments and so on
  * Similarly to the change in v0.5c, the main math font is now loaded in
    math family zero (equiv. to LaTeX's `operators` math font)
  * `\mathring` added
  * Ensure that a math font has been selected in order to prevent problems
    in minimal documents (this will be unnecessary when the OpenType LM math
    font is released)
  * Documentation for which was which of epsilon/varepsilon was backwards!
    (thank to Rasmus Villemoes for pointing this out)
  * Spurious `\upUpsilon` removed (the one at U+03A5 is now the correct one)
  * Typo when defining `\dprime` fixed
    (thanks to Ulrik Vieth for these last two)
  * Fix the math class of `\modtwosum`; it is now a large operator
    (thanks to Michael Ummels)
  * Move several LuaTeX-related patches to the `lualatex-math` package
  * Fixed mathtool's `\cramped` in XeLaTeX usage

- v0.5d (2011/01/30)

  * Assorted improvements to LuaLaTeX support, including non-growing accents
    available in LuaTeX v0.65 and later
  * Improved behaviour with reading and using maths font dimensions
  * Better compatibility with legacy maths packages and environments
    (always more worked needed, though)
  * Fix the default setting for "vargreek-shape"

- v0.5c (2010/09/27)

  * Fix a long-standing bug in XeLaTeX in which the "master" math
    families 2 and 3 weren't being set; hence fraction rules and many other
    parameters were not being set correctly
  * Stay in sync with internal fontspec changes

- v0.5b (2010/09/19): Tune-up

  * Added missing symbols/synonyms:
      \diamond  \smallint  \emptyset  \hbar  \backepsilon  \eth
  * \overline works for LuaLaTeX
  * Fix \slash; previously, it overwrote the text definition
  * \vartriangle now has the correct math class

- v0.5a (2010/07/14): TeX Live 2010 release

  * Numerous documentation improvements
  * Bug fix against stray catcode changes
  * Add `\mathcal` and `\mathbfcal` as distinct from the Script style;
    these are only supported by the XITS fonts at present
  * Small changes to the range of symbols offered (especially note that `\ac`
    is now `\invlazys` to avoid acronym package clash)
  * Superscripts are allowed after primes (as they should be)
  * Numerous LuaLaTeX improvements, including roots and over/under braces.

- v0.5 (2010/06/03): Initial CTAN release

