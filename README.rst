=====
dicey
=====

``dicey`` generates `Diceware™ passphrases
<http://world.std.com/~reinhold/diceware.html>`_. It uses the crytographically
secure ``secrets`` module. (This module ships with Python 3.6 or newer.)
And its source code is about 20 lines long, so you can easily check that
it doesn't do anything fishy.


Usage
=====

You need a Diceware™ *wordlist*, that is, a textfile containing one number
and one word per line, separated by one ore more whitespaces characters.

By default, ``dicey`` reads the wordlist from STDIN and outputs a six word
diceware passphrase::

    dicey <wordlist

You can also pass a wordlist with ``-w``::

    dicey -w wordlist

By default, ``dicey`` generates a six word passphrase,
but you can change the number of words with ``-n``::

    dicey -n 12 <wordlist

By default, ``dicey`` separates words with spaces,
but you can set another deliminator with ``-d``::

    dicey -d- <wordlist


Wordlists
=========

You can download wordlists at <http://world.std.com/~reinhold/diceware.html>.

You can also generate your own.

Given a plain textfile with one word per line:

Firstly, check that the wordlist is useful, that is, contains enough words::

    sort -u <wordlist | wc -l

``wc`` should report at least about 8000 lines.
If your wordlist has less words, get more.

Secondly, create an enumerated list::

    awk '{print NR " " $0}' wordlist >enumerated

This file is suitable as input for ``dicey``.
It is *not* suitable for rolling your own dice.


Getting ``dicey``
=================

Disclaimer
----------

You use ``dicey`` **at your own risk**. You have been warned.


Download and Installation
-------------------------

``dicey`` is a simple Python 3 script. It should work on any operating system,
provided you got Python 3.6 or newer.

Download the repository from:
<https://codeload.github.com/odkr/dicey/tar.gz/v1.0.1>

Then copy ``dicey`` to a directory in your ``PATH``,
*/usr/local/bin* is a good choice, and make it executable.

You can do this by saying::

    curl https://codeload.github.com/odkr/dicey/tar.gz/v1.0.1 | tar -xz
    # Check the source!
    more dicey-1.0.1/dicey
    # If -- and only if -- you like what you see, continue by:
    sudo mkdir -pm 0755 /usr/local/bin
    sudo cp dicey-1.0.1/dicey /usr/local/bin

There isn't much of a point in keeping the repository around,
so you may then wish to say::

    rm -rf dicey-1.0.1


Documentation
=============

``dicey`` has a ``--help`` option.


Contact
=======

If there's something wrong with ``dicey``, `open an issue
<https://github.com/odkr/dicey/issues>`_.


Legal
=====

This is free software released into the public domain.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.


Further Information
===================

GitHub:
<https://github.com/odkr/dicey>
