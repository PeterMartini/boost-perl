boost-perl
==========

Boost.Perl - A boost library for Perl

This is, for now, a work in progress to propose to Boost.

At a high level, the goal is to create a library similar to Boost.Python, enabling easy C++ integration with Boost libraries and without touching XS.

The project will have 2 kinds of targets: a standard Boost.pm/Boost.so library, which will only have to be loaded once regardless of how many other modules use the Boost library, and any number of <project.pm>/<project.so> modules which will require only the Boost.Perl headers.

This means the top level Boost.pm module can be distributed via CPAN or packaged by the OS, and all that a compiled module needs is the requisite headers and a Makefile.PL dependency on the appropriate version of Boost.

*Note also* - if the module doesn't peek under the covers, using only the Boost <-> Perl module interface layer, that means binary modules can be run between different Perl major versions, and potentially even between Perl 5 and Perl 6, since the Boost <-> Perl module binary compatibility layer will be stable even if the Perl Interpreter <-> Boost layer is not.
 
