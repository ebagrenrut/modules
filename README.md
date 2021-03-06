Modules, provides dynamic modification of a user's environment
==============================================================
[![Build Status](https://travis-ci.org/cea-hpc/modules.svg?branch=master)](https://travis-ci.org/cea-hpc/modules)
[![Coverage Status](https://codecov.io/gh/cea-hpc/modules/branch/master/graph/badge.svg)](https://codecov.io/gh/cea-hpc/modules)

The Modules package is a tool that simplify shell initialization and
lets users easily modify their environment during the session with
modulefiles.

Each modulefile contains the information needed to configure the shell for
an application. Once the Modules package is initialized, the environment can
be modified on a per-module basis using the module command which interprets
modulefiles. Typically modulefiles instruct the module command to alter or
set shell environment variables such as PATH, MANPATH, etc. modulefiles may
be shared by many users on a system and users may have their own collection
to supplement or replace the shared modulefiles.

Modules can be loaded and unloaded dynamically and atomically, in an clean
fashion. All popular shells are supported, including bash, ksh, zsh, sh,
csh, tcsh, fish, as well as some scripting languages such as tcl, perl,
python, ruby, cmake and r.

Modules are useful in managing different versions of applications. Modules
can also be bundled into metamodules that will load an entire suite of
different applications.


Quick examples
--------------

Here is an example of loading a module on a Linux machine under bash.

    $ module load gcc/6.1.1
    $ which gcc
    $ /usr/local/gcc/6.1.1/linux-x86_64/bin/gcc

Now we'll switch to a different version of the module

    $ module switch gcc gcc/6.3.1
    $ which gcc
    /usr/local/gcc/6.3.1/linux-x86_64/bin/gcc

And now we'll unload the module altogether

    $ module unload gcc
    $ which gcc
    gcc not found

Now we'll log into a different machine, using a different shell (tcsh).

    % module load gcc/6.3.1
    % which gcc
    /usr/local/gcc/6.3.1/linux-aarch64/bin/gcc

Note that the command line is exactly the same, but the path has
automatically configured to the correct architecture.


Getting things running
----------------------

To learn how to install modules see `INSTALL.txt` for Unix system or
`INSTALL-win.txt` for Windows

To have things running efficiently you will need a lot of additional setup.
For an example take a look at `doc/example.txt` which explains how things
have been setup at the University of Minnesota computer science department.


Requirements
------------

 * Tcl >= 8.4


License
-------

Modules is distributed under the GNU General Public License version 2 (GPL
v2). Read the file `COPYING.GPLv2` for details.


Documentation
-------------

Look at `NEWS` for summarized information regarding the changes brought
by each released version. Look at `ChangeLog` for detailed information
regarding changes.

The `doc` directory contains both the paper and man pages describing the
user's and the module writer's usage. To generate the documentation files,
like the man pages (you need Perl podlators to build the documentation),
just type:

    $ ./configure
    $ make -C doc all

The following man pages are provided:

    module(1), modulefile(4)


Test suite
----------

Regression testing scripts are available in the `testsuite` directory (you
need dejagnu to run the test suite):

    $ ./configure
    $ make test

Once modules is installed after running `make install`, you have the
ability to test this installation with:

    $ make testinstall


Links
-----

Web site:

    http://modules.sourceforge.net

GitHub source respository:

    https://github.com/cea-hpc/modules

GitHub Issue tracking system:

    https://github.com/cea-hpc/modules/issues

SourceForge project page:

    http://sourceforge.net/projects/modules/


Authors
-------

Current core developers and maintainers are:

 * Xavier Delaruelle <xavier.delaruelle@cea.fr>
 * R.K. Owen <rk@owen.sj.ca.us>
 * Kent Mein <mein@cs.umn.edu>

The following people have notably contributed to Modules and Modules would
not be what it is without their contributions:

 * Mark Lakata
 * Harlan Stenn
 * Leo Butler
 * Robert Minsk
 * Jens Hamisch
 * Peter W. Osel
 * John L. Furlani
