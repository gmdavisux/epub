## EPUB notes

These notes were origninally for me. I have been part of an epub (ebook) project twice now, a few years apart. Each time I had to learn everything over again. Since I don't do this regulary or for a living, I needed to find a way to make this repeatable, cheap and easy. 

### Helpful Links
[How to repack an epub file from command line](https://ebooks.stackexchange.com/questions/257/how-to-repack-an-epub-file-from-command-line) Really so much better than uzing a GUI zip app and renaming. The big killer is getting the mimetype file to be the first one in the archive. There are several replies to this. Read the first few to find what you need. For me, using a Mac has it's own challenges which someone already solved for me.

`zip -rX "../myprecious.epub" mimetype $(ls|xargs echo|sed 's/mimetype//g') -x *.DS_Store`

The above comand-line takes the contents of the current directory and creates a package with mimetype first, without any of the invisible Mac files. It's important you have aready used 'cd' to point to the correct folder with all your epub files.

[How to install and run EpubCheck on Mac OS X from the command line](http://rcliff.com/blog/how-to-install-and-run-epubcheck-on-mac-os-x-from-the-command-line/)
This helped me install the command line offical [EPUBCheck](https://github.com/w3c/epubcheck/wiki) app from W3C. EPUBCheck will validate the package and files within. It is a command-line tool but easy enough to use.

[W3C Epub 3.2 Specifciaton](https://www.w3.org/publishing/epub3/epub-spec.html) – IMHO, the W3C has some of the most difficult to to read and understand documentation ever created. This is not a good source but the ultimate source of truth.

[Blitz ebook Tricks](https://friendsofepub.github.io/eBookTricks/) I have only just started to look at this. Looks to be a great resource. There is a ling list of helpful CSS to fix thinkgs like line height and image sizing. 

### CSS (at the moment)
I am using GoogleDocs to create the ebook. I then add a cover image and the additional CSS below to fix the issues I see. (lots form Blitz link above) I also want to alter all of the GoogleDocs css but alas they are not trying to output eficient code. I'd liek to replace it all with my own and not include the external fonts (but provide a font stack). That will come but for now, here it is. 

            body {
                line-height: 1.5;
            }

            body * {
                line-height: inherit;
                font-kerning: normal;
                font-variant: common-ligatures oldstyle-nums proportional-nums;
                font-feature-settings: "kern", "liga", "clig", "onum", "pnum";
            }
            a.text-color {
                color: inherit;
                -webkit-text-fill-color: inherit;
            }
            img{object-fit: contain; max-width: 90%; max-height: 90%;}
            h1, h2, h3{
                line-height: 1.5;
                page-break-after: avoid;
                page-break-inside: avoid;
                break-after: avoid;
                break-inside: avoid;
                adobe-hyphenate: none;
                -webkit-hyphens: none;
                -moz-hyphens: none;
                -ms-hyphens: none;
                -epub-hyphens: none;
                hyphens: none;
            }
            h1{break-before: always; page-break-before: always;}
            sub {
                font-size: 0.675em;
                line-height: 1.2;
                vertical-align: sub;
                vertical-align: -20%;
            }

            sup {
                font-size: 0.675em;
                line-height: 1.2;
                vertical-align: super;
                vertical-align: 35%;
            }
