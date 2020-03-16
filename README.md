## EPUB notes

These notes were origninally for me. I have been part of an epub (ebook) project twice now, a few years apart. Each time I had to learn everything over again. Since I don't do this regulary or for a living, I needed to find a way to make this cheap and easy. 

### Helpful Links
[How to repack an epub file from command line](https://ebooks.stackexchange.com/questions/257/how-to-repack-an-epub-file-from-command-line) Really so much better than uzing a GUI zip app and renaming. The big killer is getting the mimetype file to be the first one in the archive. There are several answers to this. read the first few to find what you need. For me, using a Mac has it's own challenges which someone already solved for me.
`zip -rX "../myprecious.epub" mimetype $(ls|xargs echo|sed 's/mimetype//g') -x *.DS_Store`

[How to install and run EpubCheck on Mac OS X from the command line](http://rcliff.com/blog/how-to-install-and-run-epubcheck-on-mac-os-x-from-the-command-line/)
This helped me install the command line offical [EPUBCheck]() app from W3C. EPUBCheck will validate the package and files within.

[W3C Epub 3.2 Specifciaton](https://www.w3.org/publishing/epub3/epub-spec.html) – IMHO, the W3C has some of the most difficult to to read and understand documentation ever created. This is not a good source but the ultimate source of truth.

[Blitz ebook Tricks](https://friendsofepub.github.io/eBookTricks/) I have only just started to look at this. Looks to be a great resource. 
