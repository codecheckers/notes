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
is to copy a recent one from another repository (e.g. <https://github.com/codecheckers/covid19model-nature/blob/master/codecheck.yml>). even
better, to use our R package, that will help you create the
certificate.

To use our R package, you will need R and latex.  In a fresh R
session, do:

```
install.packages("remotes")
remotes::install_github("codecheckers/codecheck")
```

This will install the master version of our package.  Then quit R, and
restart it in the root level of the repository and run the following:

```
require(codecheck)
create_codecheck_files()
```

Further details are available in our vignette
`codecheck_overview.Rmd`. [link](https://rdrr.io/github/codecheckers/codecheck/f/vignettes/codecheck_overview.Rmd)


The R package can also help with submitting the certificate and metadata to
zenodo.


## Compile the certificate

In the `codecheck/` folder, simply run `make` to generate
codecheck.pdf.  Currently the difficult bit is importing the figures
and tables into your codecheck, for which you need to look at previous
examples.  I (SJE) am working on a simpler workflow.

## Uploading to zenodo

The R package contains code for uploading the metadata and certificate
to Zenodo.  You don't need to use  this, but it should be quicker (and
less error prone) than typing in the metadata.

### Get a Zenodo token

To communicate with R, you will first need to get an API token from
Zenodo.  (If you have a working token, skip this step).

1. Login to Zenodo with your orcid or github account:
<https://zenodo.org/account/settings/applications/tokens/new/>
2. Give a unique name, e.g. "codecheck" and under the scope, select
   all three Scopes.
3. HIt "Create" to get the access token (a long alphanumeric string).  Treat
   this like a password and keep it safe.  
4. Write it into a local file, or store it in a password manager, such
   as [pass](https://www.passwordstore.org/).  Do not upload it to
   github!! e.g. you could store the following in `~/zenodo-token.txt`
   
```
abbbbabbbb897348979797981723894798798
```

5. Follow the steps in `codecheck/codecheck-zenodo.R` to (1) create a
   new Zenodo record, (2) upload metadata (3) upload certificate.



## Getting help

If you are stuck, don't hesitate to ping Stephen or Daniel with a
query.
