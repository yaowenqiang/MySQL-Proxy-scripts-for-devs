MySQL Proxy scripts for devs
============================

This is a repository of useful [MySQL Proxy][mysql-proxy] scripts targetting
mainly developers in quest of debugging.

Requirements
------------

[MySQL Proxy][mysql-proxy]

Running
-------

mysql-proxy --proxy-lua-script=/absolute/path/to/the/script.lua

Scripts
-------

### debug.lua

Prints every SQL command received while cleaning obsolete spaces. Every
command appears on one line with the following additional information:
* an optional informative message about the query,
* the number of rows returned or affected by the query,
* the amout of time (in ms) it took to run the query.

Additionally, colors are used to provide direct information on the queries:
* yellow: when not using a good index (no\_good\_index\_used flag),
* yellow + bold: when not using an index at all,
* red: when an error occured,
* pink: for queries affecting records.

Colors are also used to denote slow queries: time displayed in red instead of
green. When a query returns no rows nor affect records, "<NONE>" is displayed
using red in reverse video.

[mysql-proxy]: http://forge.mysql.com/wiki/MySQL_Proxy