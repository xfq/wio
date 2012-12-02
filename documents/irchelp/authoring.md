---
title: www.irchelp.org content guidelines and authoring information.
author: Stephanie Daugherty
summary:	>
	Content guidelines and authoring information for irchelp.org contributors and staff.
---

# Authoring Documents for www.irchelp.org
*This is an early draft of this guide, documenting the new way we're going to maintain www.irvhelp.org. Suggestions are welcomed. Unless otherwise noted, this really isn't set in stone yet, so now is the time to give your input!*
* * *

## Introduction

This site is run by a group of volunteers primarily consisting of the ops from the #irchelp channel on EFNet. We welcome contributions to the site, but have a number of guidelines which you should
follow so that your content can be easily included into the site.

## Migration Plan

*This document currently describes the plans for the new and improve www.irchelp.org. The rest of this document uses present tense, since it will become the "how to write for us" guide of the new site. --Stephanie*

*This section will be archived once the migration is complete.*

There have been some hard decisions with this migration. Several months back, we were considering moving to a real CMS like Drupal, and I was one of the cheerleaders behind such a move. It was a great plan, but the problem is, like many great plans, we lacked the initative to follow through.

irchelp.org suffers from a series state of neglect, going back at least as far as 1994 if not further. With a static site, this neglected state makes us look abandoned, and less useful to our audience. With a dynamic site however, the same level of neglect would be disasterous, and would long ago have led to our site becoming a platform from which to launch attacks on others, as well as a platform from which our site visitors could be exploited. This is not a disaster I wish to see happen, and the ball being dropped with the CMS transition brought a cold dose of reality to our plans. irchelp.org has been terribly neglected and irchelp.org will likely be terribly neglected again, so let's make the best of what we can.

After evaluating the possible alternatives to a CMS, the solution of a static site generator came to mind. We serve very little dynamic content, and the dynamic content we do serve has been effectively retired (we had a CGI for a searchable EFNet channel listing that's probably busted now). Other than that, the site is static content - hundreds of pages that basically never, or almost never change.

### Conclusions

 * After 6 months with the move to Drupal stalled by neglect, and 15 years of general disrepair before that, it's clear that we cannot be trusted to properly maintain a website.
 * Having a single "editor" for www.irchelp.org creates a huge bottleneck which amplifies the problem of neglect.
 * The template system we use now (basically appending a header and footer to each file by copy and paste) is not maintainable, and creates a huge problem of inertia around any changes.
 * We need to lower the cost of becoming an "editor" so that any interested #irchelper can get started doing it in an afternoon.
 * Executable and script downloads on the site are dangerous - we have no reliable way to detect tampering, and no digital signatures, and even if we had them, we are not paying close enough attention to do anything about it.


### The plan so far

*This serves mostly as a "where we are at" on the project, as things have been hashed out over the mailing list and over IRC. While not set in stone, and input is still very much welcome, significant time has been spent debating and implementing these decisions already, and there is considerable inertia behind many of the decisions made, and any changes that may delay the relaunch of the site may be postponed until after we're up and running on the new setup.* 

 * The existing CGI scripts, including the EFNet Channel List and the mail form will be retired as soon as possible due to serious security concerns, and the associated pages will be appropriately redirected via a landing page to appropriate resources elsewhere on the web. The mail form is rarely used anymore, and the channel list is obsoleted by better resources that didn't exist when the original channel search was created.
 * There will be no serverside code for the foreseeable future. This may be reconsidered after we have reestablished a solid history of responsible stewardship of the website, with multiple maintainers active over the course of at least several months.
 * The format for pages on the new www.irchelp.org will be the "Markdown" format plus a simple descriptive header described later in this document. This format has been chosen because it's easy to author content in, and because there are a wide number of implementations capable of processing that input into a working website, so we aren't at the mercy of any particular software developer.
 * There will be a Git repository of all site content, and read/write access to that repository will be available to #IRCHelp ops to facilitate spreading site maintainance workloads and avoid the bottleneck of having a single "editor".
 * Existing URLs will be carefully maintained, and redirects created as needed.
 * A backup of the site before the move will be carefully preserved. Additionally, we've been well preserved by the Internet Archive, [all the way back to Freesoft's time as webmaster](http://web.archive.org/web/19961219105056/http://irchelp.org/).
 * All software downloads including executables and scripts will be removed from the website, including old copies of mIRC, Windows 95/98 era hotfixes, and similar files. Redirects will be made appropriately.

### In the future
*These are changes which may come once the upgrades are complete.*

 * I'm looking at the [Gitit](http://gitit.net) wiki software as a possible editing interface for #irchelpers in the future, after we get the site up and running and into the modern era.


## Technical Information

As of 2012, all content on the site is maintained as Markdown files with a short YAML header containing metadata. [Markdown](en.wikipedia.org/wiki/Markdown) is a simple way of adding formatting to text files, very similar to wiki markup.

   The files are kept in a [Git](http://git-scm.org) repository, and automatically generated using [PieCrust](http://bolt80.com/piecrust/).

### Document Header
The document header is written in YAML, and delimited with three dashes. It is a simple list of name: value pairs that describe each document. These headers will be used in templates.

A sample header follows:

	---
	title: Document title
	author: random-irchelper
	datecreated: 1 September 1993
	dateupdated: 30 November 2012
	status: (this is optional, but I'm going to add hooks that put a warning message about depreciated content if the status is "historical")
	summary:	>
		This is a long summary with multiple lines.
		Each line is indented in the same way. When the indentation stops, so does the summary.
	---

Note the --- at the beginning and end of the header. This seperates the header from the content, and is required for PieCrust to recognize this as a header. The header is **not** Markdown formatted, so most other Markdown parsers will not format it.


## Useful tools

Several programs are useful to irchelp.org authors.

  * [retext](http://sourceforge.net/p/retext/home/ReText/) is a graphical editor with live preview for Linux systems (available in the Ubuntu repositories as *retext*).
  * [PieCrust](http://bolt80.com/piecrust/) is useful to be able to test the automatic build process, but not required for authors.



## Content Guidelines
  * We are not a software hosting site. No executables or archive files will be hosted - links should be provided to landing pages for stable and canonical download locations for any software mentioned on the site.
  * We are aiming to be as network-agnostic as possible. In the past, IRCHelp.org was EFNet and IRCNet centric, we are in the process of changing that.

## Legal Requirements

Going forward, in order to protect ourselves from any legal trouble and avoid having to scramble to remove articles, we need to have clear rights to use all content on irchelp.org. This can take one of two forms - the content may be generally licensed under terms that permit anyone to use it - public domain or an acceptable free documentation license, or the content may be provided to irchelp.org under a release that grants us a non-revocable right to publish it.

  * Content must either be your own work, or under an acceptable free documentation license, or we can't host it.
  * For content you have created yourself, we ask that you either release it under one of our acceptable licenses, listed below, or provide a release giving us a non-exclusive, royalty-free, perpetual right to publish your content on our website.

### Acceptable Licenses
  * CC-BY
  * CC-BY-SA
  * GFDL
  * Public Domain
  * Others?

* * *