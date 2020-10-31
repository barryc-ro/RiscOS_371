
Found this on the internet, thought it deserved some love.

Build-able RISC OS 3.71, includes ROM, disc components and all the compilers/
assemblers needed to build them.

Build requirements

1) A RISC OS machine, 26-bit addressing OS, 3, 4 and 6, not 5. Tested on 3.71
2) A way of copying the ,xxx file-type files in git to RISC OS, e.g. NFS
3) A filing system which only has 10 character filenames, some of the
   file-names are truncated, could be fixed later. E.g. an ADFS E rather
   than an ADFS E+ disc

The instructions in !Readme are really good, but the following is the
quick-start guide

Double-click !Env4
Double-click BuildSys.Morris4.!Config
Double-click BuildSys.Morris4.!MkClean
Double-click BuildSys.Morris4.!MkSystem

If all went well the built ROM image should have today's data as
Install.Images.4MEG
