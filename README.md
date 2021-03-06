# LESSCPY #
*python LessCss Compiler.*

v0.9a

A compiler written in python for the lesscss language. 
For those of us not willing/able to have node.js installed in our environment. 
Not all features of lesscss are supported (yet).
Some features will probably never be supported (JavaScript evaluation). 
This program uses PLY (Python Lex-Yacc) to tokenize/parse the input and is 
considerably slower than the nodejs compiler. The plan is to utilize this 
to build in proper syntax checking and perhaps YUI compressing.

This is an early version, so you are likly to find bugs.

For more information on lesscss:

 * http://lesscss.org/
 * https://github.com/cloudhead/less.js
 
Development files

 * https://github.com/robotis/Lesscpy (mainline, py3+)
 * https://github.com/bollwyvl/Lesscpy (python 2.7 fork)
 
Requirements
============

* python 2.7+
* ply (Python Lex-Yacc) 

For more information on ply:
* http://www.dabeaz.com/ply/
 
Installation
============

    pip install -e git://github.com/bollwyvl/Lesscpy.git#egg=Lesscpy
or

    pip install setup.py
 
or simply place the package into your python path.

Compiler script Usage
=====================

    usage: lesscpy [-h] [-I INCLUDE] [-v] [-x] [-X] [-t] [-s SPACES] [-o OUT] [-r]
                   [-f] [-m] [-D] [-S] [-V] [-L] [-N]
                   target

    LessCss Compiler

    positional arguments:
      target                less file or directory

    optional arguments:
      -h, --help            show this help message and exit
      -I INCLUDE, --include INCLUDE
                            Included less-files (comma separated)
      -v, --verbose         Verbose mode

    Formatting options:
      -x, --minify          Minify output
      -X, --xminify         Minify output, no end of block newlines
      -t, --tabs            Use tabs
      -s SPACES, --spaces SPACES
                            Number of startline spaces (default 2)

    Directory options:
      Compiles all *.less files in directory that have a newer timestamp than
      it's css file.

      -o OUT, --out OUT     Output directory
      -r, --recurse         Recursive into subdirectorys
      -f, --force           Force recompile on all files
      -m, --min-ending      Add '.min' into output filename. eg, name.min.css
      -D, --dry-run         Dry run, do not write files

    Debugging:
      -S, --scopemap        Scopemap
      -V, --debug           Debug mode
      -L, --lex-only        Run lexer on target
      -N, --no-css          No css output


Supported features
==================
* Variables
* String interpolation
* Mixins
* mixins (Nested)
* mixins (Nested (Calls))
* Guard expressions
* Parametered mixins (class)
* Parametered mixins (id)
* @arguments
* Nesting
* Escapes ~/e()
* Expressions
* Keyframe blocks
* Color functions:
  * lighten
  * darken
  * saturate
  * desaturate
  * spin
  * hue
  * mix
  * saturation
  * lightness
* Other functions:
  * round
  * increment
  * decrement
  * format '%('
  * add
  * iscolor
  * isnumber
  * isurl
  * isstring
  * iskeyword

Differences from lessc.js
=========================
* All MS filters and other strange vendor constructs must be escaped
* All colors are auto-formatted to `#nnnnnn`. eg, `#f7e923`
* Does not preserve css comments

Not supported (yet)
===================
* mixins (closures)
* Pattern-matching
* JavaScript evaluation

License
=======
See the LICENSE file

<jtm@robot.is>
