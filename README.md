# GuideML 3.15

AmigaGuide to HTML converter for Haiku

Authors:
 * shred@chessy.aworld.de (Richard Koerber)
 * chris@unsatisfactorysoftware.co.uk (Chris Young)
 * pulkomandy@gmail.com (Adrien Destugues)

This version was ported to Haiku using a set of Amiga/BCPL wrapper headers to
redirect function calls. This allows sharing part of the sourcecode with the
Amiga version. However, the GUI had to be removed, and some extra changes to the
source were made.

The ReadArgs stuff is copied from AROS sourcecode, with minor changes.

## Documentation

AmigaGuide to HTML file converter, with lots of features including:

  - 100% C, no compiled ARexx stuff or anything like that.
  - Source code is included, under GNU General Public Licence.
  - Converts any AmigaGuide compliant documentation into a multi or single-
    file HTML 4.01 Transitional document (UNIX and MS-DOS compliant)
  - Can link correctly to external AmigaGuides
  - Supports Amigaguide @macros
  - Fully supports @next, @prev, @toc, @help and @index command (e.g. for
    TexInfo based guide files)
  - Supports font style (@{B},...) and colour (@{FG ...}) commands, with
    CSS style sheet support and configurable colours
  - Detects Internet (http, https, ftp, mailto, ...) links
  - Detects E-Mail addresses
  - Navigation bar with "CONTENTS", "INDEX", "HELP", "RETRACE", "NEXT",
    "PREV" and "HOME" buttons (also as footer if you like)
  - Navigation titles freely changeable. You can also insert images!
    (A free set of images will automatically be generated.)
  - Navigation bar can be switched off, and/or you can have a Site
    Navigation Bar (supported by Mozila)
  - The <body> tag is changeable, and you can add header/footer text
    to every page
  - @WORDWRAP and @SMARTWRAP guides convert correctly
  - MS-DOS file suffix is generated optionally (.htm)
  - Lots more!


## CHANGES SINCE 3.11:

### V3.15 (21.06.2008)

* It is now possible to blank out navbar labels to prevent certain links from being shown.

* A tab between the node name and title was not being recognised as whitespace.

* Macro arguments not enclosed in quotes would crash GuideML.

* GuideML did not always pick up the line number in links.


### V3.14 (10.05.2008)

* Fixed various aspects of single file creation: line numbering, links to
  external documents, nodes with names which start with "main", tidy up of
  anchor names, now creates files called <guidename>.html in the specified
  directory instead of main.html.

* Input file requester now has a hook function to detect AmigaGuide files
  instead of relying on the name only.

* Fixed some memory leaks

* Reversed the order the macro list is searched (local macros now get
  priority)

* Fixed the NUMBERLINES tooltype


### V3.13 (04.05.2008)

* Added macro support.  AmigaGuide commands within macros will be
  translated to HTML as expected, and macros within macros are allowed,
  as are macros with arguments and both local and globally defined macros.
  You can also use macros to replace AmigaGuide commands as per the
  AmigaGuide specification.

* Added line number links support.  You need to enable adding line
  numbers to HTML files with the NUMBERLINES/Number lines in HTML option
  as it makes the files bigger for no benefit if you don't use line number
  references.

* \@font is now supported (as global and local attribute).

* Added \@{amigaguide} command.

* Saving a project now uses a def_guideml icon if found, and uses the
  short forms of the command line arguments where available.

* Fixed "prepend ../" option, which wasn't working in all cases.


### V3.12 (30.04.2008)

* Added "Prepend external links with ../" option to enable multi-file
  AmigaGuides to be converted, by converting each file into a directory
  named the same as the orignal file in lowercase.

