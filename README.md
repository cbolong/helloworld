# helloworld
This is a sample code.

1. Create helloworld source code.

2. Run "autoscan" to create configure.sacn, then rename configure.scan to configure.ac
$ autoscan
$ ls
autoscan.log  configure.scan  README.md  src
$ mv configure.scan configure.ac

Note: configure.ac is needed by aclocal .
Add " AC_CONFIG_FILES([Makefile])" before AC_OUTPUT

3. Run "aclocal" and "autoconf" to create "aclocal.m4"/"configure" files.
$ aclocal
$ ls
autom4te.cache  autoscan.log  configure.ac  README.md  src
$ autoconf
$ ls
autom4te.cache  autoscan.log  configure  configure.ac  README.md  src

4. Create Makefiles.am
SUBDIRS=src

5. and create src/Makefiles.am
bin_PROGRAMS=hello
hello_SOURCES=hello.c

6. Create dependency files.
$ touch README AUTHORS NEWS ChangeLog

7. Create common header (config.h.in)
$ autoheader

8. Run "automake --add-missing" , base on Makefiles.ac , produce Makefile.in
$ automake --add-missing

9. Run configure to create makefile
$ ./configure --host=${TARGET_HOST} --prefix=$PWD