# Instructions to the codechecker

These notes are to help a codechecker perform a codecheck of a
project.

## Pre-requisites

Before you can start as a codechecker, you will need a few essentials:

1. Ensure you have an ORCID account.
   [Register](https://orcid.org/register) if you don't have one (it
   takes 30 seconds).
   
2. [Sign up](https://github.com/codecheckers/codecheckers/issues/new?assignees=nuest&labels=registration&template=codechecker-registration.md&title=Register+as+codechecker)
   as a codechecker on github.  For this you will need a github
   account.

## Start a new codecheck

Assuming you have all the details from the AUTHOR to start a codecheck
(code/data/instructions), then you can do the following:


1. Clone the AUTHOR's repository (e.g. clone github.com/author/brainscans
into github.com/codecheckers/brainscans).
2. Open an issue to state that you wish to start a codecheck.
   (Remember to close this ticket after you have published the certificate.)
3. Edit the codecheck register to get a new codecheck certificate
   number.  Link to the issue that you created above.


## Run their code

Now the tricky part.  Run the AUTHOR's code to check that you can
reproduce the relevant outputs (figures/tables) from their code.  You
do not need to do a detailed comparison of the outputs -- as long as
some outputs are generated, that is enough to pass the test.  (You may
wish to comment on any differences you found to the author before
finishing.)

Do keep a note of any particular software that you needed to install
or any extra steps you needed to take that were not documented by the
AUTHOR.

If you find any problems, you can report the error to the author --
you are not expected to fix their bugs.  Of course, if there are any
trivial problems (e.g. missing packages), you may wish to fix them and
note them in your report.

## Write the certificate

We use a file `codecheck.yml` in the root directory of the project to
store the metadata for the certificate.  One easy way to create this
is to copy a recent one from another repository (e.g. xxx). even
better, to use our R package, that will help you create the
certificate.

To use our R package, you will need R and latex.  In a fresh R
session, do:

```
install.packages("remotes")
remotes::install("codecheckers/codecheck")
```

This will install the master version of our package.  Then quit R, and
restart it in the root level of the repository and run the following:

```
require(codecheck)
create_codecheck_files()
```

Further details are available in our vignette
`codecheck_overview.Rmd`. [link](https://rdrr.io/github/codecheckers/codecheck/f/vignettes/codecheck_overview.Rmd)



