rkv: command-line reference manager
===================================

Planned features
----------------

- Command-line interface (CLI), similar to Git or Taskwarrior.

- SQLite backend.  It MUST be possible to perform searches on your own using
  SQL queries.

- Emphasis on LaTeX compatibility.  It MUST be possible to run the command from
  a Makefile to generate a LaTeX bibliography file.

- Support for multiple languages.  Some fields MAY have different values
  depending on the selected language (titles and abstracts especially).

- Support for series and periodicals as additional document types.  Relations
  between different documents (citation keys) MUST be explicit.  For example,
  entries for articles MUST reference their journal rather than specifying the
  information about the journal themselves.

- Support for report series.  It MUST treat technical reports as items in a
  series.  Accession numbers and report codes MUST be included in the database.

-------------------------------------------------------------------------------

Copyright © 2020 Andrew Trettel
