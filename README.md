essentials
==========
it's not required to install all of essentials, just install what you need based on language of your project.

php
---
first of all install php code sniffer:

`pear install PHP_CodeSniffer`

*note*: as rules / hook may change during time, do NOT copy them directly, instead use soft link.

`cd /path/to/pear/PHP/CodeSniffer/Standards/`

`ln -s /path/to/xamin-std/phpcs-rules/Xamin Xamin`

python
------
you need to be able to run pep257 and pep8 commands, install them from:
http://pypi.python.org/pypi/pep8
https://github.com/everplays/pep257

javascript
----------
http://www.jshint.com/

git-hook
========
`cd /path/to/your/git/project/.git/hooks/`

`ln -s /path/to/xamin-std/git-hooks/pre-commit pre-commit`

*note*: you can ignore this hook with --no-verify switch.

