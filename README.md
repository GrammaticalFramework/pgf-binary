# pgf-binary
Custom version of the binary-0.5 package for the PGF library

## Description

This is a layer on top of "Data.Binary" with its own 'Binary' class and customised instances for 'Word', 'Int' and 'Double'.
The 'Int' and 'Word' instance use a variable-length encoding to save space for small numbers.
The 'Double' instance uses the standard IEEE754 encoding.

## History

From _Thomas Hallgren_, November 2018:

> I did some work back then ~2015 to make GF more modular. This included:
> - Eliminating mutual dependencies between the GF.* and PGF.* modules to make it possible to factor out the PGF library into a separate package. src/runtime/haskell/pgf.cabal was created as part of this. It still works I think, but it is not used, AFAIK.
> - I also separated out Krasimir's fork of the binary package into a separate directory src/binary. I explored two possibilities:
>   - Removing this fork entirely. I added the custom-binary flag in gf.cabal, which allowed you to switch between the standard binary package and Krasimir's fork, to make it easy to compare the difference in performance and size of .gfo and .pgf files.
>   - Replacing it with a thin layer on top of the standard binary package. This is the pgf-binary.cabal package in src/pgf-binary.
> 
> I didn't complete this work back then because there was nothing that could replace the convenience of building everything with a single 'cabal build' command if you split up the code into several Cabal packages.

On 2018-11-07 this was [moved out of the gf-core repository](https://github.com/GrammaticalFramework/gf-core/commit/422248f11fdb1aa76af72bee67d30ea8d63fa892) into here, in case we ever need it again.
