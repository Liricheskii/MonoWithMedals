Overview
========

This is source code of audiosurf 2 "mono with medals" mod. There is only
script files, full mod you can download from Steam Workshop. But here you
can also find script for testing and some technical information.

Files
=====

"mono with medals.lua" is absolutely identical to the same file from game mod.
It copies default mono mode script but has some additioncal calculations. Since
most part of this file is not intresting for us this calculations were copied to
the "test.lua" file. This file can be launched via any lua interpreter and
contains only calculations which are specific for this mod. That`s why it
is very easy to debug and improve this mod.

Mod logic
=========

The main idea is very simple - we just build game tree with fixed max depth
and looking for highest score in the leafs. Then we decide collect or skip
current block and go for the next iteration. This algorithm works fine during
most part of the song but can lose many points on powerblocks. The most obvious solution
is to increase max depth near PB`s but it has too big computational complexity
because size of game tree grows exponentially. So if we want to look 30 blocks
forward it will take 2^30 iterations... and this is very big number. I put some commentary
in source code so if you don`t underastand something they may help.

PS
==

If you have any suggestions, ideas or bug reports feel free to post them on mod page in
Steam Workshop. I have few ideas how to improve calculations but they not that easy in
implementation. So i don't think i'll do something now alone unless someone inspires me
somehow.
