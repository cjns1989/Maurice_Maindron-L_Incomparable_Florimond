# About Maurice Maindron

Maurice Maindron (1857-1911) spent his younger days working for the French Museum of Natural History, travelling the world to collect zoological samples mostly in Africa and the Far East. He gave up the position at some point in the early 1890s and became a writer both of fiction and non-fiction with a special interest in the history of late 16th and early 17th century France. His extensive knowledge of the areas of historical costume, weaponry, architecture, heraldry and all aspects of everyday life during the late Middle Ages and the Renaissance together with the scientific approach and attention to detail that he had acquired during his years as a zoologist have led some critics to coin the term *archaeological novels* (as opposed to the traditional genre of *historical* novels) to better describe Maindron's objectives and production.

# Structure 

  The book's source is organised along the following lines:

      (...)
        └── novel title         →  title of the novel 
            ├── css             →  style sheets (epub)
            ├── epub            →  epub created by pandoc
            ├── fonts           →  default publisher's fonts (epub)
            ├── html            →  html created by pandoc
            ├── images          →  covers: cover.png (epub), cover_4x3.png (pdf) 
            ├── latex           →  latex files created by pandoc
            ├── md              →  markdown source (pandoc flavor)
            ├── pdf             →  pdf(s) created by pandoc ("raw" pdf — i.e. with no cover image)
            ├── pdfc            →  pdf(s) created by pandoc (with cover image)
            ├── xml             →  metadata.xml (epub)
            ├── zip             →  zipped archive of the pdf directory ("raw" - text-only pdfs)
            ├── zipc            →  zipped archive of the pdfc directory (with cover image added)
            ├── README.md       →  this README file in github's markdown format
            └── Makefile        →  set of rules to build html, epub, and pdf versions of the novels

# Building

  If you are only interested in reading the novel, the master branch already has the current state-of-the art version available (in html, epub, and pdf format) in the corresponding subdirectories.

  In the event you wish to make any changes (fix annoying typos, modify the contents of source files, improve the formatting, specify a different font, provide your own cover images... etc.) and ready your own version for publication you could do the following:

  1. git clone the project (or download/unpack the zip file)
  2. make your changes
  3. navigate to the top of the book's directory and execute the following commands from the shell prompt:
     - make clean
     - make *target*

  ... Where *target* can be any of the following:

  1. make (ibid. *make all*): recreate all the output files (html, epub, pdf...) in one pass
  2. make *allpdf*: recreate all the pdf output (raw and with cover image)
  3. make *epub*: recreate the epub
  4. make *html*: recreate the web-friendly html output

  While working on changes rather than run *make all* and create all output formats (which may take time on slow systems) you can create a single pdf file at one given point size - e.g. *make pdf10* to create the 10pt raw pdf.

  By default the pdf and pdfc folders each contain 6 files — at different point sizes: 8, 9, 10, 11, 12 & 14pt.

  The zip archives can also be recreated separately by pointing make to the *zip* and *zipc* targets.

# Software dependencies

  The **build** process described above relies on the presence of the following programs:

  1. bash (or a compatible shell)
  2. GNU make
  3. sed
  4. pandoc
  5. latex/xelatex
  6. pdftk
  7. imagemagick
  8. img2pdf

  These tools are either installed by default by current GNU/linux distributions or available from their standard repositories.

  The default font used both for the epub and the pdf output is the classic **EB Garamond** font originally by Austrian designer Georg Mayr-Duffner. This default font can easily be changed to suit your requirements by editing the css style sheet (epub) or the makefile (pdf — cf. the LATEX_FONT variable).
  
  Note, that a number of default values can easily be changed to suit your requirements by editing the variables specified at the beginning of the makefile.
