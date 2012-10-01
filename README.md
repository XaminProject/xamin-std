Installation
=============
first of all install php code sniffer:
`pear install PHP_CodeSniffer`

as rules / hook may change during time, do NOT copy them directly, instead use soft link.

Rules
-----
`cd /path/to/pear/PHP/CodeSniffer/Standards/`
`ln -s /path/to/xamin-std/phpcs-rules/Xamin Xamin`

git-hook
--------
`cd /path/to/your/git/project/.git/hooks/`
`ln -s /path/to/xamin-std/git-hooks/pre-commit pre-commit`

*note*: you can ignore this hook with --no-verify switch.

checking a file manualy
-----------------------
`phpcs --standard=Xamin file.php`

example
-------
take a look at `php-cs example` directory

Install jshint
==============
http://www.jshint.com/
