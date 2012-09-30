Install phpcs 
=============
via pear : pear install PHP_CodeSniffer

copy phpcs-rules/Xamin directory into pear/PHP/CodeSniffer/Standards

for check a file use this command : phpcs --standard=Xamin file.php
see phpcs example folder 


Install jshint 
==============
http://www.jshint.com/ 

GIT pre-commit file
===================
copy this file into YOUR git repository (YOUR working copy) .git/hooks folder and make it executable.

you can ignore this hook with --no-verify switch. 
