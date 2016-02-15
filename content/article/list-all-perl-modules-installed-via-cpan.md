{
   "authors" : [
      "David Farrell"
   ],
   "description" : "A quick way to list all non-core modules installed via CPAN using the command line:",
   "slug" : "14/2013/4/7/List-all-Perl-modules-installed-via-CPAN",
   "date" : "2013-04-07T18:52:11",
   "draft" : false,
   "tags" : [
      "cpan",
      "module",
      "sysadmin",
      "old_site"
   ],
   "image" : null,
   "title" : "List all Perl modules installed via CPAN"
}

A quick way to list all non-core modules installed via CPAN using the command line:

``` prettyprint
perldoc perllocal
```

Note that if you are using perlbrew and have several different versions of Perl installed, the perllocal command will only output modules installed for the active Perl version. If you execute the perllocal command and see this:

``` prettyprint
no documentation found for "perllocal"
```

This means that no non-core Perl modules have been installed via CPAN. Try installing a module via CPAN, and then retry the perllocal command.

