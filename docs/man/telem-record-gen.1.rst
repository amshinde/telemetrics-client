================
telem-record-gen
================

------------------------------
Create custom telemetry record
------------------------------

:Copyright: \(C) 2017 Intel Corporation, CC-BY-SA-3.0
:Manual section: 1


SYNOPSIS
========

``telem-record-gen`` <options>


DESCRIPTION
===========

Generate and attempt to send a telemetry record to ``telemd``\(1). This
program can be used to create a telemetry record from a shell script
or from another program using e.g. ``system()``. The program connects
to a local ``telemd``\(1) daemon to spool the record for delivery to
the actual collection service.

The payload can be provided as standard input, as a file with the
``--payload-file`` option, or as a string argument with the ``--payload``
option. If neither the ``--payload`` or ``--payload-file`` is provided,
the payload is assumed to be on <stdin>.

Each record is expected to have a class identifier, a record version
number, and a severity level. A class identifier is required to be
provided.


OPTIONS
=======

 * ``-h``, ``--help``:
   Show help options.

 * ``-V``, ``--version``:
   Print the program version.

 * ``-f``, ``--config-file`` <file>:
   Path to configuration file (not implemented yet).

 * ``-s``, ``--severity``:
   Severity level (1-4) - (default 1).

 * ``-c``, ``--class``:
   Classification ``level_1``/``level_2``/``level_3``.

 * ``-p``, ``--payload`` <payload>:
   Record body (max size = 8k).

 * ``-P``, ``--payload-file`` <file>:
   File to read payload from.

 * ``-R``, ``--record-version`` <version>:
   Version number for format of payload (default 1).

 * ``-e``, ``--event-id`` <version>:
   Event id to use in the record. If not provided a randomly generated id will be assigned to record.



RETURN VALUES
=============

0 on success. A non-zero exit code indicates a failure occurred.


SEE ALSO
========

* ``telemd``\(1)
* https://github.com/clearlinux/telemetrics-client
* https://clearlinux.org/documentation/

