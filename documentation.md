---
layout: frontpage
title: {{ site.title }}
---

# Documentation

## System Documentation

* Coming soon...

## Background Papers

* [10 Page Introduction to Trusted Computing](http://www.cs.ox.ac.uk/files/1873/RR-08-11.PDF) is a nice, brief paper that overviews the basics of trusted
  computing.
* [Principles of Remote Attestation](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.298.2277) is an overview paper discussing philosophy and implementation directions for remote attestation.
* [Semantic Remote Attestation](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.1.4055) is the seminal initial work on remote attestation.

## Layout

Description of repositories and wikis used for the project.

### Repos

* `armoredsoftware.github.io` - Website repo that contains the project
  website.
* `admin` - Administrative cruft.  This is the only repo that is not
  publicly available.  Students need not have access to this repo.  
* `doc` - System documentation.  Design documents, presentations,
  capability descriptions, and formal documentation.  Current
  documentation should always be on the `main` branch.
* `code` - All code for the system.  Source code, Makefiles,
  configuration files, scripts, and anything else required for
  building the base ArmoredSoftware system.  Current system should always be
  on the `main` branch.

Remember that only the `admin` repo is private.  All other repos are
available to the general public.

### Wikis

* `admin.wiki` - Administrative wiki.  This is the only wiki that is
  not publicly available.  Students need not have access to this repo.
* `doc.wiki` - Public ArmoredSoftware wiki.  Meeting notes are here as
  well as general notes on development and informal documentation.
  Add pages here for documenting design decisions and discussions.
* `code.wiki` - Research notebook wiki.  Each developer should have a
  wiki page here where they document their development activities.
  
Remember that only the `admin.wiki` is private.  All other wikis are
available to the general public.

## Environment

Description of our working environment.

*Coming soon*

## Information for Students

Student specific information.

### What *done* means

If you are asked *is a development task done*, here are your criteria
for deciding:

1. Code compiles and runs in our standard working environment
1. Makefiles are up-to-date and support system building
1. Code has been tested in our standard working environment
1. Code is checked into the proper repository
1. Documentation is checked into the proper repository
1. Test cases installed for nightly build testing

Not being done is usually okay.  Saying you're done when you don't
meet the *done* criteria is always bad.

### ITTC and Core Hours

Students need to be in the laboratory during core hours 10am-3pm
during weekdays.  The only exceptions being classes and one-time
activities.  When you work other than that is up to you, but you will
certainly need to work more than just core hours.  Some of you will be
nocturnal, some will be morning people, and in quite rare cases you
might actually work 8-5.  We don't care as long as you're around for
core hours.  If you're not going to be around, make sure you adviser
knows.

During the academic year please hang around Nichols when you're not in
class.  You are welcome to use ITTC resources for classwork, hold
meetings in the lab, and generally treat the lab as your home as long
as it does not interfere with our work.

### Meetings

We will schedule project meetings once a week.  You need to be there
and let your advisor know if for some reason you're not.  Chances are
advisers will also meet with their groups separately.  How that is
structure is up to you and your ad-visor.

### Tools

1. `emacs` - for papers and code.  Use `auctex` mode for LaTeX.
`reftex` is also exceptionally useful for managing bibliography
files. Use the standard markdown mode for markdown files.
1. `latex` - for papers and documentation.  Use the `natbib` package
for bibliographies and references.  Use `flyspell` for on-the-fly
spell checking.
1. `bibtex` - for references.  We will maintain a BibTeX database that
will be common across the project in the `doc` repository.
1. `markdown` - for documentation, wikis, and we pages
1. `git` - for repository management.  Commit often and branch for new
code development.
1. GitHub - for repository hosting.  We will share all of our code and
papers for the project under the armored software group.  You must
have a GitHub id to work with our repositories.

### Publication

Publication is the currency of academia and we will publish
frequently.  Here are some guidelines for papers:

1. Author lists are students first and faculty second.
1. Author lists should always err on the side of being inclusive.
1. Publications written for the project should always include one or
   more faculty advisers.
1. Always acknowledge the sponsor using the footnote:

*This work in sponsored by the United States Department of Defense,
 contract number H98230-13-C-0264*
