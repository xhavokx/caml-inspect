OCaml Inspect - caml-inspect.
======================================================================

Inspect is a small library to inspect arbitrary OCaml values and their
associated object graph by either dumping them as S-expressions (with
sharing and references), or by writing output in the DOT-language
which can then be further processed by [Graphviz](http://www.graphviz.org/).

Inspect was originally written by Kaspar M. Rohrer (<kaspar.rohrer@gmail.com>).

Caml-inspect is hosted on [Github](http://github.com/krohrer/caml-inspect/).

Installation
------------

Unzip or untar in any directory, then run

    make

to generate the library and documentation.
To install the library using findlib, simply type

    make install

And to uninstall it

    make uninstall

For development, you may instead run

    sudo ln -s `pwd` `ocamlfind printconf path`/inspect

Usage
-----

If you have findlib installed, using the library is as simple as
typing

    #use "topfind";;
    #require "inspect";;

into your OCaml prompt. I suggest you open the Inspect module as well.

    open Inspect;;

For starters, both the Dot and the Sexpr library provide a test_data
function to generate some interesting data to dump.

    Sexpr.dump (Sexpr.test_data ());;
    Dot.dump (Dot.test_data ());;

It is naturally also possible to let the dump functions inspect
themselves:

    Sexpr.dump Sexpr.dump;;
    Dot.dump Dot.dump;;

If you are on a Mac, the Inspect.Dot.dump_osx function should be of
interest. It writes the DOT output to a temporary file, uses Graphviz
to generate the graph, and displays the results using the open
command.

    Dot.dump_osx Dot.dump_osx;;

It goes without saying that you should have Graphviz installed for
this last part to work.

For more information, you should build and view the documentation.

    make htdoc

License & Distribution
----------------------

> This library is free software; you can redistribute it and/or
> modify it under the terms of the GNU Lesser General Public
> License as published by the Free Software Foundation; either
> version 2.1 of the License, or (at your option) any later version,,
> with the special exception on linking described in file LICENSE.

> This library is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
> Lesser General Public License for more details.
 
> You should have received a copy of the GNU Lesser General Public
> License along with this library; if not, write to the Free Software
> Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
