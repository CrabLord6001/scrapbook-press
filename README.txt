SCRAPBOOK PRESS
===============

A single-file program for laying out scrapbook pages: pick a template,
add photos to its zones, write as much or as little as you want, then
export print-ready pages at true physical size.

It runs entirely on your own computer.


INSTALLING
----------

There is no installer. Put scrapbook.html wherever you want it to live
and double-click it. It opens in your web browser and runs from there.

Suggested setup — keep one folder per book:

    Scrapbook 2019/
        scrapbook.html          <- the program
        2019.scrapbook.json     <- your project (layouts + photos)
        photos/                 <- your originals

Back up that folder and you have backed up everything.

Chrome or Edge are the best choice: they let the program save directly
back to your project file. Firefox and Safari work, but every save lands
in your Downloads folder instead.


PRIVACY
-------

The program makes no network connections of any kind. There are no
accounts, no sign-in, no uploads, no analytics, no external fonts or
scripts. Your photos are read from your disk by the browser and stay
there; your writing is only ever in your project file.

You can confirm this yourself: open scrapbook.html in a text editor and
search for "http". The only matches are the XML namespace on the drawing
icons, which is an identifier, not an address. There is no fetch(), no
XMLHttpRequest, no WebSocket. You can also disconnect from the internet
entirely and the program works exactly the same.


USING IT
--------

Templates...    Choose a layout for the current page. Photos and writing
                already on the page are re-used in the new layout where
                they fit.

Your own        Build a page however you like -- start from Blank, add
templates       zones, set your frames, fonts and tilts -- then open
                Templates... and choose "Save this page as a template".
                It keeps the layout and styling and leaves your photos and
                writing out, so you can use it again on any page.

                Your templates are kept in this browser, and they are also
                written into your project files. Open one of your projects
                on another computer and its templates come with it.

Adding photos   Tap "Add photo" on any empty zone to pick a file -- on a
                phone that opens your camera roll. "Add photos" in the
                toolbar fills several empty zones at once.

                On a computer you can also select several photos in a
                folder and drag them onto the page together; they fill the
                empty zones in order, so a four-photo layout fills in one
                motion. Dropping onto empty space creates a new photo.

Cropping        Drag inside a photo to re-center it. Pinch, scroll-wheel,
                or use the Zoom slider, to crop in and out.

Text            Click a text zone and type. No length limit. Font, size,
                alignment and color are in the panel on the right.

Zones           Nothing is fixed. Select a zone to move it (blue bar),
                resize it (corner handles), rotate it, duplicate it or
                delete it. "+ Image" and "+ Text" add new ones anywhere,
                which is also how you add clipart and stickers — PNG files
                with transparent backgrounds are detected and shown whole
                rather than cropped.

Pages           The strip on the left holds the pages. Add, duplicate,
                reorder and delete them there.

On a phone or tablet the two side panels become drawers: the menu button
at the top left holds your pages, and selecting a zone brings up an
"Edit this zone" button at the bottom right with all of its settings.
Phones work for adding photos and writing; laying out a page is far
easier on a real screen.


SAVING
------

Save as...      Choose where your project file lives. Do this once, early.
Save (Ctrl/Cmd+S)
                Writes back to that same file. The file name in the
                toolbar shows a dot when you have unsaved changes.

In Chrome and Edge it also saves itself back to that file every minute.
There is a second safety net: the program keeps a copy inside the browser
and offers to restore it if you close the tab by accident.

WHAT A BROWSER CLEANUP CAN AND CANNOT TOUCH

Clearing cookies and site data, or running a cleaner, erases two things:
the in-browser spare copy, and your template library. It can NEVER touch
a project file you have saved -- that is an ordinary file on your disk,
as safe as a photo or a Word document.

So the rule is simple: get your work into a file early. The program will
nag you every few minutes until you have.

Templates have two safety nets of their own. They are written into every
project file, so opening any project brings them back, and "Back up
templates" in the Templates window writes them to a file you can keep
with your projects. "Restore..." reads that file back, and importing the
same backup twice will not create duplicates.


EXPORTING
---------

PNG         The current page as an image at 300 DPI.
Export PDF  All pages, or just this one, as a PDF. Each page is a true
            physical page -- a 12x12 project produces 12x12 inch PDF
            pages, which is what a print shop or photo-book service wants.
            300 DPI is the right setting for printing; 150 is fine for
            sending someone a proof.

What you see while editing and what comes out of the export are drawn by
the same code, so the printed page matches the screen.


A NOTE ON PHOTOS
----------------

Photos are reduced to 2400 pixels on their longest side when you add them.
That is more than enough for a sharp 8-inch print at 300 DPI, and it keeps
project files a reasonable size. It does mean the project file is not an
archive of your originals -- keep those.


KEYBOARD
--------

Ctrl/Cmd + S     save
Ctrl/Cmd + D     duplicate selected zone
Delete           remove selected zone
Arrow keys       nudge (hold Shift to nudge further)
Page Up / Down   previous / next page
Esc              deselect
