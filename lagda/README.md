* The (literate) `*.lagda` files are used to generate the `html` pages with the script `../build`.

* This script also generates (illiterate) `../agda/*.agda` files using the script `illiterate`, which calls the Haskell program `illiterator.hs`.

* The program `agdatomd.hs` converts from `.lagda` to `.md` for use by the script `fastloop`.

* This script is used for editing the notes in conjunction with `jekyll serve` so that after an update it is only necessary to reload the page on the brouwser to view it.

* The script `slowloop` serves the same purpose, but calls Agda instead of `agdatomd`, via the script `generatehtml`, to that we get syntax highlighting in the html pages. This can be very slow depending on which `lagda` file is changed. This means that after the first reload, one is likely to see the Agda code without syntax highlighting.

* It is possible to run `./slowloop`, `./fastloop` and `jekyll serve` in parallel, and we do this for editing these notes.

* The loop scripts use `inotifywait` to detect `lagda` file changes and trigger the appropriate conversion actions.
