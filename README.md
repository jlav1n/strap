Bootstrap 2.3.2 Template for Interchange
========================================

This is the Div based Demo for Interchange that modernizes the old
standard template. It makes use of several newer technologies. jQuery is
included by default. All table-related layout has been replaced with
divs. Built on the Bootstrap Framework, version 2.3.2:

        http://getbootstrap.com/2.3.2/

You can download a customized Bootstrap, and drop it into the
html/boostrap directory, to load your own colors, etc:

        http://getbootstrap.com/2.3.2/customize.html

Created by [Perusion](http://perusion.com), based on the earlier
standard demo.

Copyright (C) 2013 Hanson Investments, Inc. d/b/a Perusion

This program is offered without warranty of any kind.
See file LICENSE for redistribution terms.

Usage:
------

Clone the repository (or download the ZIP file and extract) to your
Interchange directory (e.g. /usr/local/interchange). From there, run:

	bin/makecat --demotype=strap [your-catalog-name]

Some of the changes include:
----------------------------

* Consolidated LEFTRIGHT, LEFTONLY, NOLEFT TOP & BOTTOM variables into
  single TOP & BOTTOM. No longer need "templates/regions", and moved
  defines into existing "variables/". Changes in templates can still be
  hard coded in BOTTOM, but the long-present but seldom-used
  "display_class" in individual page headers is used more now.

* Templates leftright, leftonly, noleft, formerly located in
  "include/layout" have been moved to more appropriately named
  "templates/layout". This is to consolidate the directory structure and
  make location of templates more intuitive. Can be easily changed to be
  more backward-compatible if desired by simply editing
  "variable/BOTTOM"

* No longer using THEME_CSS.

* All pages, components, forms (everything!) updated to use
  Bootstrap styles and markup, with HTML5.

* Uses ISO-8859-1 charset by default, to avoid problems with UTF-8 and
  Perl. You can easily re-enable UTF-8 by uncommenting the lines in
  catalog.cfg. Be sure to test all functions for errors, and use at
  your own risk!

* [bootmenu] tag to show menus using Bootstrap-compatible styles. No
  more messy inline Javascript for dropdown menus.

* Product Groups and Categories use the "ncheck" subroutine in
  catalog.cfg to allow pretty URLs, such as /Tools/Hand-Saws, rather
  than scan/search URLs.

* SEO-friendly "more" paging: no more unindexable "more" pages, nor need
  to use PermanentMore. Now, "more" pages are: /2, /3, /Next, /Previous.
  Also provides canonical and "rel=prev/next" meta tags.

* New /All-Products link.

* Searches are now sent as GET requests, not POSTs. Also now uses
  SearchProfile for very short URLs -- search query is sent in the "s"
  parameter, for easy tracking via Google Analytics.

* Old product forum has been removed.

* Use of UserDB's "indirect_login" by default, to allow emails as
  usernames (uses a new 'usernick' column).

* Uses UserDB crypted passwords by default. (The default users in
  userdb.txt won't work, unless you edit their passwords from the
  Admin, so they are saved as encrypted.)

* Password Reset page no longer emails password (impossible with crypted
  passwords). Now sends a basic encoded link to reset the password,
  which expires in 1 day.

* Checkout pages have a ton of clean up, and improved with user-
  experience guidelines. No more "old_browser" checks, nor *_multi
  include files.

* Multi-page checkout is the default. No more ord/multi.html. The
  Shipping Address page (ord/shipping.html) now has a login prompt
  at the top.

* One-page checkout is still included and accessible from the top menu.
  However, it is only recommended if you have a shipping setup that does
  not depend on a geographical location; if your shipping changes
  based on country/state/ZIP, etc, it will not refresh the page to
  obtain the correct rates. Javascript-based page refreshing is not
  reliable with modern browers and their auto-fill functions.

* Google Analytics included if GOOGLE_ANL_ID variable set.

* Profiles moved to include/profiles/

* Gift certificates (pay certs) supported out-of-the-box. Several code
  improvements, including ability to validate certificate's check_code
  and expiration, and ability to pay for entire order or part of order
  with a gift cert.

* Stock Alert function updated to use a database table and Job to email
  when item is back in stock.

* Address Book (member/ship_addresses.html, etc) and Saved Carts have
  been removed. We found these features were too complex and little-used
  in their current state.

* Admin order_view page updated to show gift_note, tracking_number, and
  pay_cert totals.

* Admin "Content" tab is hidden, since old Content Editor not really
  supported anymore.

* Survey function has been removed.

* Page to reconfigure catalog: pages/test/recon.html

* Page to show shipping information: pages/test/ship.html
