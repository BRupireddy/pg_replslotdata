# pg_replslotdata
Tool for displaying replication slot information. Replication slots data is stored in binary format on the disk under pg_replslot/<<slot_name>> directory in PostgreSQL's data directory which isn't human readable. If the server is crashed/down (for whatever reasons) and unable to come up, currently there's no way for the
user/admin/developer to know what were all the replication slots available at the time of server crash/down to figure out their restart_lsn, xid, two phase info or types of slots etc. This tool helps interpret the replication slots information and displays it onto the stdout even if the server is crashed/down. The design of this tool is similar to the other PostgreSQL core tools available today i.e. pg_controldata, pg_waldump etc.

Compatibility with PostgreSQL
=============================
Version 14 and above.

Installation
============
Easiest way to compile the code is to copy it as src/bin/pg_replslotdata in PostgreSQL source code and use "make install".

Usage
=====
./pg_replslotdata -D data_dir

Run ./pg_replslotdata --help for all options and their usage.

Dependencies
============
No dependencies.

LICENSE
=======
pg_replslotdata is free software distributed under the PostgreSQL Licence.

Copyright (c) 1996-2022, PostgreSQL Global Development Group

Developer
=========
This extension is developed and being maintained by Bharath Rupireddy.

- Twitter: https://twitter.com/BRupireddy
- LinkedIn: www.linkedin.com/in/bharath-rupireddy

Bug Report: https://github.com/BRupireddy/pg_replslotdata or <bharath.rupireddyforpostgres@gmail.com>
