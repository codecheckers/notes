# Instructions to the author

These notes are to help an AUTHOR initiate a codecheck of their work.


(<https://codecheck.org.uk/guide/community-process> has an earlier
version).


## What we need to start a CODECHECK

- Link to the paper that you wish us to codecheck.  Ideally the paper
should be open access, as we prefer not to link to papers behind
paywalls unless strictly necessary.  We are happy to codecheck preprints.

- Contact details for who we can talk to if there are issues running the
code.  Our codecheck philosophy is very much that if we can't get code
to run, we will tell you what problems we had and hope that you can fix
them.  "We investigate, not fix".  Of course, some matters may be
trivial for us to fix (e.g. a missing R package), in which case we will
do so.

- Link to the code and data for us to run.  It is easiest (but not
essential) if the code is on a repository like github or gitlab.  Please
ensure that the code and data are public, or that you are happy to make
them public by the time the certificate is finished.  Please include a
licence for your code and data.

- A README describing how we should run the code.  The following items are
helpful to include in the README:

1. Versions of any software that are required, and operating systems
that you have used.  We primarily use linux for our codechecks, but if
e.g. your work requires a particular operating system, a CODECHECK might
still be possible.

2. Tell us how the outputs relate to your paper (e.g.  "Run the script
analysis.m to generate figures/output.pdf which should match Figure 2 of
the paper.")  As a minimum, at least one figure or table should be
reproducible for us to write a codecheck certificate.  Not all figures
need to be reproducible.  If your work involves stochastic computations,
either provide a seed for the random number generator, or simply note
the fact that jobs are stochastic.  Providing Makefiles or similar
workflow descriptions are also helpful, but not essential.

3. Typical run times (e.g. minutes, hours, weeks) and hardware that you
  have run the code on.  Please note we cannot routinely codecheck
  papers that take many days of compute time; if your jobs are of that
  scale, please talk to us about resources.
  

## What happens next

Our workflow for performing a codecheck is to clone your project and put
most of our files in a directory called "codecheck" in the root of your
project, along with "codecheck.yml" in the top-level of the project.  If
you wish to help us, you may wish to create a codecheck.yml file to
store the above information in a machine-readable format. See
e.g. <https://github.com/sje30/covid19model-report23/blob/master/codecheck.yml>
for a recent example; you need only provide information in section 1; we
will complete section 2.  Providing a codecheck.yml file however at this
stage is not a requirement.

During the codecheck, we will contact you if we need help, and to
clarify any issues arising.

