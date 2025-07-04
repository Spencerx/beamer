# Changelog
All notable changes to this project since v3.50 will be documented in this
file.

The format is based on [Keep a
Changelog](https://keepachangelog.com/en/1.0.0/), version strings comprise
a major and minor version only.

## [Unreleased]

### New

- added `height=...` options for `columns` and `column` to set a fixed height

### Changed
- Definition of `\beamer@label@in@display` to track `amsmath` changes

## [v3.74]

### Fixed

- added missing `mini frame in current section` templates for `box` and `tick` (fix #940)
- adopt workaroud for changed label definition in amsmath from https://chat.stackexchange.com/transcript/message/67866940#67866940 (fix #941)

## [v3.73]

### Fixed

- fixed issue of block body not adapting to surrounding pgf fill opacity
- fixed section title alignment in tree and smoothtree outer themes if combined with a split-based outer theme
- fixed incorrect uncovering of rounded shadow blocks after `\pause`, see https://tex.stackexchange.com/q/745623/36296

## [v3.72]

### Added

- doc: added sentence about limitations of xelatex
- added `bgopacity` option to `beamercolorbox` and `beamerboxesrounded` for transparent background drawing
- allow optional argument for the default `block begin`, `block example begin` and `block alerted begin` templates

### Changed

- unified usage of `(sub)section in head/foot` template in headlines
- simplify decision tree for `\beamer@howtotreatframe` (see #874)
- added `\maketitle`, `\title`, `\author`, `\institute` and `\date` to the exceptions for `ignorenonframetext`
- avoid frame breaks between block title and body for rectangular blocks
- added `\gdef\@currentHref{#2}` to labels (see #917)
- fine-tune vertical space around section title in miniframe headline (close #895)

### Fixed

- fixed problem if inmargin theme is used with the `usepdftitle=false` class option (see #885)
- fixed spacing problem for right-aligned frametitles without background colour
- fixed missing `\newline` if ragged2e is used together with beamerarticle (#900)
- defined `\fnum@table` to avoid breaking longtable (#905)
- fixed: other sections would show the template for "miniframe in other subsection" instead of "mini frame in other section"
- fixed unstable text position in sidebar theme by compensating for the space automatically inserted after the frametitle in https://github.com/josephwright/beamer/blob/main/base/beamerbaseframe.sty#L126

## [v3.71]

### Changed

- scale height of tree and split headlines with fontsize of `section in head/foot`

### Fixed

- ensure that shadows of rounded blocks use proper black for their shadow
- using correct template for `\structure` in article mode (see #862)

## [v3.70]

### Added

- making the aspect ratio available to the user via `\insertaspectratio`
- adding `title`, `author`, `institute`, `date` and `titlegraphic` templates to make title page easier to customise

### Changed

- smoothbars outer theme: moved the shading between headline and frametitle a bit down to avoid the miniframe appearing clipped off in some pdf viewers
- made top shading of Singapore theme transparent (see #782)
- scale height of infolines headline with fontsize of `section in head/foot`
- calculate the head/footheight at the start of each frame instead of only at the start of the document
- making `\part` compatible with `\nameref`

### Fixed

- adding strut to the `frame number` and `page number` footlines to avoid jumping (see #840)
- fixed bug in `inmargin` inner theme which would show the author indicator even if the author was empty

## [v3.69]

### Fixed

- protect the frametitle continuation so it can be used with \MakeUppercase (see #802)
- first aid for metropolis theme (see #802)
- fixed indentation of multiline section titles in `square` and `ball unnumbered` toc templates (see #817)
- using `bibliography entry ...` font in biblatex generated bibliographies

## [v3.68]

### Changed

- simplified non-text links for navigation symbols and framezoom
- doc: re-organised section about navigation symbols
- moved parts of `beamerbasenavigation.sty` to `beamerbasenavigationsymbols.tex`

### Fixed
- fixed height of non-text links to prevent overlaps in vertically stacked miniframes (see #780)
- avoid problem with non-black black (see #772 and #659)

## [v3.67]

### Changed
- beamer sets \@currentlabelname itself and no longer relies on nameref patches.

### Fixed
- slide transitions if the new pdfmanagement is used
- name of transition replace in pdf is R not Replace

## [v3.66]

### Fixed

- fixed edge case in numbering of hidden and unnumbered frames (see #756) 
- fixed regression of class options not being passed to packages like xcolor (see #759)

## [v3.65]

### Added

- adding new `onlytextwidth` class option to use this key for all `columns` environments by default (see #731)
- adding new stretchable frame option `s` (see #696)
- adding user-accessible commands for `\beamersidebarwidth` and `\beamerheadheight` (see #537)
- allow custom values for `aspectratio` option (see #549)

### Fixed

- using `gray` colormodel for the delcarartion of fadings (workaround for #718)
- fixed bullet colour of alerted items for custom item colour (see #735)
- workaround to make miniframes clickable in xelatex (see #332)
- added missing encoding value to multimedia sound macro (see #607)
- improved problem with shadow of blocks without title (see #647)
- reduced artefacts in poppler based viewers for shadow blocks (see #647)
- workaround to make `\framezoom` clickable in xelatex (see #619)
- exclude invisible frames from being counted (see #592)
- fixed cut off miniframes for 8pt and 9pt (see #752)

## [v3.64]

### Added

- new continuation count template "singleframecheck" which will only show the continuation count if a break actually occurs (see #423)
- new template for lined note pages (#704)

### Changed

- added `aspectratio=2013` class option setting the frames' aspect ratio to 20:13 (see #497)
- Remove redefinition of `\addtocontents` (see #698)
- patched macros from the `pdfpages` package to automatically remove the frame background for the included pages
- transparent shadows for smoothbars outer theme (see #717)
- transparent shadows for smoothtree outer theme (see #720) 
- added new beamer option "show only slides with notes", the old class option "notes=onlyslideswithnotes" now gives an obsolete warning like all the other note options (see #724)
- make footnotetext and footnoterule adapt to the current column with (see #713)
- using `mathversion{sf}` for the kpfonts package (fix #711)

### Fixed

- solved font-dependant problem with shadow boxes (partial fix for #647)
- adding hook rule for polyglossia to compensate for the different execution order of the new hook system (see #706) 

## [v3.63]

### Changed

- adding `lastsection` option to toc (#675)

### Fixed

- Removed superfluous period in combination with the `firstsection` option (#674)
- Behaviour of `\label` in article mode (#685)
- Problem with date position in infolines theme (#684)

## [v3.62]

### Fixed
- Issue with naming of file hooks (#670)
- fixed problem with `\insertmainframenumber` in combination with `ignorenonframetext` (see #665)

## [v3.61]

### Fixed

- `\beamer@bibiconwidth` already defined bug (see #652)
- shadowboxes and transparent overlays (see #654)
- workaround for misalignment of biblatex with sidebar theme (see #645)
- bug with nonshadow rounded boxed (see #660)

## [v3.60]

### Changed

- added translations for author, institute and date indicator of inmargin theme (see #616)
- re-introducing transparent shadows from v3.51 (see #492)

### Fixed

- Margins in frame title color box (see #614)
- adding font substitution (see #630)
- delaying fixes for biblatex styles until the bibliography (see #625)

## [v3.59]

### Changed

- added `\transfly` macro for `Fly` page transition (see #609)
- Preparations for LaTeX2e 2020-10-01

## [v3.58]

### Changed

- re-introduced `\strut` after the frametitle (see #535)
- Promote bookmark level for index (see #554)
- clip `\insertslideintonotes` to show only visible area
- using biblatex filehooks to make adjustments to the bibliography appearance (see #581)

### Fixed

- Avoid loop with overlayarea in vmode (issue #580)
- Handling of `\\` in article mode (issue #582)

## [v3.57]

### Changed

- More patch for `paralist` package (see #539)

### Fixed

- Replace `\mode` with `\only` (see #543)
- Reset the width of color box in case of change in `\hsize`

## [v3.56]

### Changed

- Improved parser for overlays

### Fixed

- Add missing commands with overlay specification (see #525)
- Replace fixed text width in `inmargin` theme (see #529)
- Treatment of `+` and `.` overlay specifications (see #538)

## [v3.55]

### Fixed

- Inner behaviors for shaded ToC
- Fix optional arguments of `\frame` in `beamerarticle` (see #509)
- Compact glue settings for lists
- Turn off font substitution for `unicode-math` package (see #508)

## [v3.54]

### Changed

- Add the instructions of `proof begin` and `proof end` template
- Patch for `paralist` package

### Fixed

- Wrong frame number by `noframenumbering` option (see #450)
- Missing `nokeywords` option in the article mode
- Vertical glues by `allowframebreak` option (see #325)
- Typos and bad boxes in the documentation (see #491, #504 and #505)
- Revert the addition of `\input` and `\include`

## [v3.53]

### Fixed

- Behavior of `bg` key

## [v3.52]

### Fixed
- Behaviour of `\inst` (see #489)
- Incorrect shadows when using DVI routes (see #492)

## [v3.51]

### Changed
- Add `\include` and `\input` to commands respected in 'skipping' mode
- Dynamically calculate note page size (see #487)

### Fixed
- Properly set space in rounded boxes
- Enable transparency in shadows (see #466)
- Restore `\secname` in `\sectionentry`
- Apply color correctly to page number (see #468)
- Support for `noxcolor` with `beamerarticle` (see #483)
- Treatment of mixed overlay/alert specifications

[Unreleased]: https://github.com/josephwright/beamer/compare/v3.74...HEAD
[v3.74]: https://github.com/josephwright/beamer/compare/v3.73...v3.74
[v3.73]: https://github.com/josephwright/beamer/compare/v3.72...v3.73
[v3.72]: https://github.com/josephwright/beamer/compare/v3.71...v3.72
[v3.71]: https://github.com/josephwright/beamer/compare/v3.70...v3.71
[v3.70]: https://github.com/josephwright/beamer/compare/v3.69...v3.70
[v3.69]: https://github.com/josephwright/beamer/compare/v3.68...v3.69
[v3.68]: https://github.com/josephwright/beamer/compare/v3.67...v3.68
[v3.67]: https://github.com/josephwright/beamer/compare/v3.66...v3.67
[v3.66]: https://github.com/josephwright/beamer/compare/v3.65...v3.66
[v3.65]: https://github.com/josephwright/beamer/compare/v3.64...v3.65
[v3.64]: https://github.com/josephwright/beamer/compare/v3.63...v3.64
[v3.63]: https://github.com/josephwright/beamer/compare/v3.62...v3.63
[v3.62]: https://github.com/josephwright/beamer/compare/v3.61...v3.62
[v3.61]: https://github.com/josephwright/beamer/compare/v3.60...v3.61
[v3.60]: https://github.com/josephwright/beamer/compare/v3.59...v3.60
[v3.59]: https://github.com/josephwright/beamer/compare/v3.58...v3.59
[v3.58]: https://github.com/josephwright/beamer/compare/v3.57...v3.58
[v3.57]: https://github.com/josephwright/beamer/compare/v3.56...v3.57
[v3.56]: https://github.com/josephwright/beamer/compare/v3.55...v3.56
[v3.55]: https://github.com/josephwright/beamer/compare/v3.54...v3.55
[v3.54]: https://github.com/josephwright/beamer/compare/v3.53...v3.54
[v3.53]: https://github.com/josephwright/beamer/compare/v3.52...v3.53
[v3.52]: https://github.com/josephwright/beamer/compare/v3.51...v3.52
[v3.51]: https://github.com/josephwright/beamer/compare/v3.50...v3.51
