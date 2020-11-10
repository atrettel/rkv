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


Planned commands
----------------

- `rkv init [DATABASE_FILE]`

    - Create an empty database file.  If no arguments are given, this creates a
      new database in the default location if one does not already exist there.

- `rkv find option1:"field" ...`

    - List basic information, one entry per line, on all documents that match
      the arguments.

    - If only a single argument is given, it is treated as the citation key.

- `rkv list CITATION_KEY [LANG_CODE]`

    - List full information on a document.  If the language code is
      unspecified, use the default language.

    - If a partial citation key is given and there are multiple documents that
      satisfy it, list all of them on a single line each, akin to the `rkv
      find` command.

- `rkv add CITATION_KEY [type:DOC_TYPE] [language:LANG_CODE] [option1:"field1"]
  ...`

    - Add information to the database about a particular document.  Any
      additional options past the document type and language are parsed using
      the `modify` commands.  If the document type or language codes are
      unspecified, it uses the defaults.

- `rkv modify CITATION_KEY [language:LANG_CODE] [option1:"field1"] ...`

    - Modify existing information on a document.  Specifying a language code
      other than the one used to add the document adds additional fields in
      that language to the database.

- `rkv rm CITATION KEY`

    - Remove an existing document from the database.

- `rkv mv OLD_CITATION_KEY NEW_CITATION_KEY`

    - Change the citation key for a given document.

- `rkv view CITATION_KEY`

    - View the PDF of a document if available.

-------------------------------------------------------------------------------

Copyright © 2020 Andrew Trettel
