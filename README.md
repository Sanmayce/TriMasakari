# TriMasakari
Smooth Scroll Walker, Linux/Windows GUI viewer

![TriMasakari_r3_Fedora36](https://github.com/Sanmayce/TriMasakari/assets/14062548/6b59a7fb-2995-4ffa-b7d1-77fbc5c6743c)

```
README.DIZ
___________        .__    _____                            __                    .__ 
\__    ___/_______ |__|  /     \  _____     ___________   |  | _______   _______ |__|
  |    |   \_  __ \|  | /  \ /  \ \__  \   /  ___/\__  \  |  |/ /\__  \  \_  __ \|  |
  |    |    |  | \/|  |/    Y    \ / __ \_ \___ \  / __ \_|    <  / __ \_ |  | \/|  |
  |____|    |__|   |__|\____|__  /(____  //____  >(____  /|__|_ \(____  / |__|   |__|
                               \/      \/      \/      \/      \/     \/             

This is a short description of Trimasakari revision 5: the QB64&C smooth scrolling file viewer.
In order to honor the legendary Toshiba T3200 luggable laptop (owned one), here comes TriMasakari with its Amber Plasma "Theme".
In the package, ELF/EXE binaries are included, full sourcecode as well.
Trimasakari is an 100% free Smooth Scroll File Walker for Windows/Linux (and Mac, no binary inhere, though).
.
The target (developed on, also) computer was ThinkPad 11e 5th Gen - a superscamp (a la supertramp), called 'Djudjeto' - a poorpeople laptop with 1366x768 LQ display:
- Celeron N4100 (4 cores) @ 2.4GHz, GeminiLake [UHD Graphics 600], 8 GB DDR4 RAM, nvme SSD 2TB. Love this machinette!
The central idea is to have a simplistic (regarding GUI and superlow memory footprint) sidekick allowing viewing a given file in four modes:
- WRAP (actually, truncated to a fixed length) mode #1: ASCII field, its HEX equivalent field, the OFFSET (from the start) field;
- WRAP (actually, truncated to a fixed length) mode #2: Widened ASCII field, the OFFSET (from the start) field;
- RAW mode: Showing logical lines as physical ones, that is, each screen line is a [CR]LF line, i.e. non-wrapped and non-truncated;
- FOLDER mode (if CLIPBOARD (or CommandLine) houses PATH): Showing three sections:
  First, the tree structure, in pseudo-graph form, of the given folder and its sub-folders.
  Second, listing of all files, recursively taken, prefixed by their file size and path.
  Third, statistics, for the drive housing the given folder.
.
Since r5, MagScope (Magnifying Glass) was added, also after the successful compression/decompression an agent visually confirms it.
Since r.4+, the ASCII codepage is 'Gesch' (a.k.a. Schpitz), in the package there is a console tool/convertor 'UTF8toGesch' (invokable from Trimasakari).
GRAPHEMES of Gesch codepage allow browsing German/Italian/French/Spanish/Bulgarian (and its dialect Russian :P) under ASCII.
.
Switching between the two WRAP modes happens with 'Backspace';
Switching between any of the WRAP modes and RAW mode happens with 'Double-Left-Shift' or Right-Mouse-Button.
.
A quick question:
How do you read the "environment" i.e. (surrounding text) of a found needle into a haystack?
In other words, with assistance of what tool/editor, do you read the paragraphs within (e.g. Wikipedia XML dump, currently a single file 90+GB in size)
containing the search pattern "metal fatigue"?
.
As lacking as it may sound, the reality is there is no proper tool giving the Context (the environment) of the found Needles/Patterns.
The mere reporting of line numbers or the logical lines where the Needles/Patterns are found is not enough, many times one wants to EXPLORE what is around them.
.
Quick keyboard input:
- Use 'Escape' to exit;
- Use 'Alt+Enter' or 'Double-Left-Alt' to toggle fullscreen/window mode;
- Use 'Double-Left-Control' to get basic statistics for the current file, as number of lines/words and some more,
  also creates wrapped version of the file being viewed (ready to be viewed in another instance of TriMasakari);
- Use 'Double-Left-Shift' to toggle WRAP/RAW mode, WRAP is a forced one i.e. a truncator, whereas RAW shows logical lines as physical lines;
- Use 'Backspace' to toggle short/wide text field;
- Use 'Home/End/PageUp/PageDown' for going to top/end of file;
- Use 'Left/Right' to select a preset color (out of 256);
- Use 'Up/Down' to Smooth-Scroll one line;
- Use 'Spacebar' to run/pause Automatic-Smooth-Scroll downwards;
- Use 'Control+Up/Down' to set brightness for current color;
- Use 'F' to change font;
- Use 'Enter' to toggle inverse line (auto-hidden when the page is scrolled), when active then search sequence is allowed;
- Use SLASH i.e. '/' (when inverse line is active) to enter editing current line mode, the resultant string is the Needle i.e. the search pattern,
  use 'Right-Shift' release to start searching;
- Use 'Z','X','C' for 2x,3x,4x MagScope (Magnifying Glass), at the moment, this is only in RAW mode and FOLDER mode;

' This is the layout for Russian/German Phonetic - transparently accessible via 'Enter' (toggle Latin/Russian) in Edit Mode of Inverse Line:
' German letters are mapped onto '1','2','3','4' keys:
'   +--+ +--+ +--+ +--+ +--+                          +--+ +---------+
'   |~Ё| |!Ä| |@Ö| |#Ü| |  |                          |+Ъ| |Backspace|
'   |`ё| |1ä| |2ö| |3ü| |4ß|                          |=ъ| |         |
'   +--+ +--+ +--+ +--+ +--+                          +--+ +---------+
'     +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+
'     |QЯ| |WШ| |EЕ| |RР| |TТ| |YЫ| |UУ| |IИ| |OО| |PП| |{Ю| |}Щ| ||Э|
'     |qя| |wш| |eе| |rр| |tт| |yы| |uу| |iи| |oо| |pп| |[ю| |]щ| |\э|
'     +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+
'       +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +-----+
'       |AА| |SС| |DД| |FФ| |GГ| |HЧ| |JЙ| |KК| |LЛ| |:Ь| |"Ж| |Enter|
'       |aа| |sс| |dд| |fф| |gг| |hч| |jй| |kк| |lл| |;ь| |'ж| |     |
'       +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +--+ +-----+
'         +--+ +--+ +--+ +--+ +--+ +--+ +--+
'         |ZЗ| |XХ| |CЦ| |VВ| |BБ| |NН| |MМ|
'         |zз| |xх| |cц| |vв| |bб| |nн| |mм|
'         +--+ +--+ +--+ +--+ +--+ +--+ +--+

- Use 'F3' (release) or 'Double-Right-Shift' (when inverse line is active) to start searching (from the line below the inverse line) in Wildcard
  Case-Insensitive Mode, ('*' and '#' wildcards allowed) - the hit could span two lines i.e. there will be no hit misses, COULD BE ESCaped/Canceled, though;
- Use 'Left-Shift' + 'Up/Down' to Rough-Scroll one line, in WRAP mode if mouse pointer is within last 17 columns then a Vertical-Scroll-Bar (unclickable, yet)
  appears;
- Use 'Left-Shift' + F5/F6 to decrease/increase the Frame Delay (controls scroll speed, when 0 fastest), in ms;
- Use 'Shift' + F3 (when inverse line is active) to search (from the line below the inverse line) the Needle non-interactively, same as 'F3' (release) or
  'Double-Right-Shift' but finds all the hits below the inverse line, COULD BE ESCaped/Canceled, though;
- Use 'Ctrl' + F3 (External Exact/Wildcard Search, when inverse line is active) to search the Needle non-interactively with Kazahana, finds the number of ALL
  the lines with a hit (or hits), the cool thing is that all the resultant hits are dumped to 'Kazahana.txt' and its pathfilename is put into CLIPBOARD, thus
  ready for launching a new instance of TriMasakari;
- Use 'Alt' + F3 (External Fuzzy Search, when inverse line is active) to search the Needle non-interactively with Kazahana, finds the number of ALL
  the lines with a hit (or hits), the cool thing is that all the resultant hits are dumped to 'Kazahana.txt' and its pathfilename is put into CLIPBOARD, thus
  ready for launching a new instance of TriMasakari;
- Use 'Double-Right-Alt' to toggle NoRetraceFlag, when 0 (which is default), Scroll Speed is almost constant ~29 FPS, when 1, then Scroll is much (10x) faster;
.
WARNING: In r4+++, actually in Kazahana there is a problem with patterns 4- in length (for exact mode) since Railgun needs 4[+] patterns (should add
         Railgun_Doublet to handle this case), SHOULD BE ADDRESSED!
.
Quick mouse input:
- Use 'Left Button Click' to underscore the line under the pointer;
- Use (Linux only still, in RAW mode, when input is Path instead of File) Left-Shift + 'Left Button Click' to compress/decompress the file under the pointer;
- Use Left-Control + 'Left Button Click' to draw vertical line under the pointer;
- Use 'Right Button (Release)' to toggle WRAP/RAW mode, WRAP is a forced one i.e. a truncator, whereas RAW shows logical lines as physical lines,
  same as 'Double-Left-Shift';
- Use 'Up/Down Wheel' to Smooth-Scroll one line, same as 'Up/Down';
- Use 'Left-Shift' + 'Up/Down Wheel' to Rough-Scroll one line;
- Use 'Mouse Button #3' to toggle inverse line (auto-hidden when the page is scrolled), when active then search sequence is allowed, same as 'Enter'.
.
Quick Notes:
Note #0: Resizable (at run-time) window, e.g. it allows your own 4K (a.k.a. UHD a.k.a. QFHD) canvas with size up to (2x236)columns x (2x29)rows.
Note #1: Both {Command-line parameter} and {Drag-n-Drop a file over the icon/launcher} have precedence over clipboard method (Note #2) of accepting.
Note #2: If the clipboard houses a valid [path]filename - it will be shown, the file being shown can be terabytes in size, the scroll needs only a 'frame'.
Note #3: There is a bug that is a feature, change the color e.g. with two Right Arrows to #044 and scroll with inversed line in order to highlight desired lines,
         the bug (of not refreshing the whole page) comes in handy.
Note #4: Running without a valid [path]filename in the clipboard the tool runs as a color/scroll benchmark, in HD mode.
Note #5: If e.g. you press Control+C in Caja/Krusader (Linux Fedora) on selected file/folder - the full path to that file/folder goes to clipboard, then just run
         Trimasakari - it will show the content of this file/folder (in streaming mode).
Note #6: The main feature is the easy on the eyes line-by-line smooth scroll, on Celeron N4100 CPU the scroll speed is 316 FPS for 170Cx21L, just press Spacebar to
         run/pause scrolling - handy to place your palm resting before the laptop touchpad.
Note #7: With the cheapest/palest HD screens, the default 8x32 font is [a] candy to the eyes, on fancy wide angles screens it is possible to tilt the screen to
         45 degrees without straining your eyes - the slenderness of font compensates.
Note #8: In next revisions will add searchability (taken from my Dirwalker tool), the idea is to browse Wikipedia XML dump, EZ!
Note #9: Currently, Trimasakari is aware of seven modes: 1] 1366x768 (HD ready) 2] 768x1366 (rotated HD ready) 3] 1280x1024 (SuperXGA) 4] 1920x1080 (FHD)
         5] 1080x1920 (rotated FHD) 6] 2x1920 x 2x1080 (UHD,QFHD,4K) 7] 2x1080 x 2x1920 (rotated UHD,QFHD,4K).
Note #A: Every 2 minutes a powersaving mode is activated, it is meant to save laptop's battery, a known issue is the delayed powering up via a mouse wheel/click,
         keyboard is okay, though.
.
To-do list:
- Lateral scrolling;
- Adding the unseen Toshiba 16x48 font, being with 2x columns and 3x rows than the original (640x400 with 8x16 or 80x25), or dubbed '6T';
- Accepting only paths (along with [path]filenames) as input, thus showing the directory content, to be mostly a rewritten 'Dirwalker'.
.
Enfun!
.
2024-March-23
.
Machinely yours,
Sanmaitze
.
F.A.Q. (Frequently Asked Questions)
.
==============================
Q: What are the search combos?
==============================
A: When Needle is not "" (i.e. not empty): once we have Needle, there are these combos (Inverse Line should be active):
- LeftShift + F3 - Activating Non-Interactive (Finds-All-Hits-Below-The-Inverse-Line-And-Stops) Internal Exact/Wildcard Search;
- Ctrl + F3 - Activating Non-Interactive (Finds-All-Hits-Within-The-File-And-Stops) External Exact/Wildcard Search;
- Alt + F3 - Activating Non-Interactive (Finds-All-Hits-Within-The-File-And-Stops) External Fuzzy Search;
- Double-RightShift or F3 - Activating Interactive (Finds-A-Hit-Below-The-Inverse-Line-And-Stops) Internal Exact/Wildcard Search;
.
=================================
Q: What are the search sequences?
=================================
A: When Needle is "" (i.e. empty): in order to have a Needle, there are these sequences:
- Step #1: Activating Inverse Line by pressing 'Enter';
- Step #2: Activating Edit Mode (Inverse Line becomes the Needle by default) by pressing '/';
- Step #3a: Activating Interactive (Finds-A-Hit-Below-The-Inverse-Line-And-Stops) Internal Exact/Wildcard Search by releasing 'RightShift';
- Step #3b: Activating Non-Interactive (Finds-All-Hits-Within-The-File-And-Stops) External Exact/Wildcard Search by releasing 'LeftCtrl';
- Step #3c: Activating Non-Interactive (Finds-All-Hits-Within-The-File-And-Stops) External Fuzzy Search by releasing 'LeftAlt';
- Step #3d: Building Pagoda tree-structure order 5 (for the first word within Needle) by releasing 'RightCtrl';
- Step #3e: RESERVED.
.
Note1: All combos work only when Inverse Line is active.
Note2: 'Internal' is slow and single-threaded, whereas, 'External' is fast and 16-threaded.
Note3: Fuzzy search in fact is Levenshtein LengthOfNeedle\4 (i.e. Edit_Distance 3\4=0 for Needle 3 bytes long, or 18\4=4 for 'Sylvester Stallone').
Note4: The Needle 'SILVESTOR STALOUNE' will have a fuzzy match in this file, since 'I' is to be replaced, 'O' is to be replaced,
	   'L' is to be inserted, 'U' is to be deleted.
Note5: Warning! Fuzzy mode is computational heavy, prepare to drain battery fast.
.
                                                                                   +-------+
                                                                                   | Enter | (Step #1)
                                                                                   +--+    |
                                                                                      +----+
                                                                        +---+ +------------+
                                                                        | / | | RightShift | (Step #3a)
                                                              (Step #2) +---+ +------------+

+----------+  +---------+                        +----------+  +-----------+
| LeftCtrl |  | LeftAlt |                        | RightAlt |  | RightCtrl |
+----------+  +---------+                        +----------+  +-----------+
(Step #3b)    (Step #3c)                         (Step #3e)    (Step #3d)
.
============================================
Q: What is an x-gram (my version of n-gram)?
============================================
A: Let's ask ChatGPT 3.5 first about the naming convention, second, see the screenshots of the TriMasakari predecessor (Gallowwalker):

Here's a list of n-grams from 1 to 10, all using Latin-based naming:

Unigram (1-gram)
Bigram (2-gram)
Trigram (3-gram)
Quadrigram (4-gram)
Pentagram (5-gram)
Hexagram (6-gram)
Heptagram (7-gram)
Octogram (8-gram)
Nonagram (9-gram)
Decagram (10-gram)

If we were to use Greek-based naming for n-grams, the list would look like this:

Monogram (1-gram)
Digram (2-gram)
Trigram (3-gram)
Tetragram (4-gram)
Pentagram (5-gram)
Hexagram (6-gram)
Heptagram (7-gram)
Octagram (8-gram)
Enneagram (9-gram)
Decagram (10-gram)

==================
Q: What is PAGODA?
==================
A: It is a text file consisting of concatenated (and properly padded) monograms, digrams, trigrams, tetragrams, pentagrams for a given word.
Speaking of PAGODA order 5 which currently is built:
.
In order to get what Pagoda tree-structure is all about, look up next files located in 'TXTs/' folder:
- 'Sub-project_Schisch.pdf' and 'Sub-project_Schisch_footer.pdf';
- 'GW_r1+++_4-GrammingA_balloon.png', 'GW_r1+++_4-GrammingB_balloon.png' and 'GW_r1+++_4-GrammingC_balloon.png'.
.
First, sub-project 'Pagoda' aka 'Schisch' aka Shin-Bashira (Heart-Pillar) of my main Textual-Madness Project 'GAMERA' is based on (or rather built of) x-grams.
This unique structure looks like this: 
.
9,999,999                               on
9,087,698                               on_the
0,939,934                               on_his
0,444,778                               on_this
0,529,688                         based_on
0,372,517                           and_on
0,302,085                            go_on
0,396,236                               on_the_other
0,143,762                               on_account_of
0,132,696                               on_the_ground
0,176,560                         based_on_the
0,143,498                           and_on_the
0,088,361                           was_on_the
0,154,080                        and_so_on
0,083,764                       s_books_on
0,079,567                      is_based_on
0,227,093                               on_the_other_hand
0,086,049                               on_the_other_side
0,083,062                               on_the_part_of
0,083,586                         books_on_cd_rom
0,016,966                           and_on_the_other
0,012,961                  encyclopedia_on_cd_rom
0,083,575                       s_books_on_cd
0,032,257                      is_based_on_the
0,014,713                      sat_down_on_the
0,083,575                  osho_s_books_on
0,027,369          for_more_information_on
0,022,680                  what_s_going_on
0,044,133                               on_the_other_side_of
0,042,008                               on_the_part_of_the
0,019,850                               on_the_edge_of_the
0,012,957                  encyclopedia_on_cd_rom_contains
0,012,485                         based_on_separate_sources_get
0,012,335                       provide_on_request_at_no
0,083,575                       s_books_on_cd_rom
0,012,957         catholic_encyclopedia_on_cd_rom
0,012,512                versions_based_on_separate_sources
0,083,575                  osho_s_books_on_cd
0,012,313               you_received_it_on_a
0,012,107                   they_may_be_on_may
0,083,564       foundation_osho_s_books_on
0,012,363              medium_it_may_be_on
0,012,313            if_you_received_it_on
.
Above 'on' Pagoda is of order 5 i.e. it houses all 1-grams/2-grams/3-grams/4-grams/5-grams with central beam/word being 'on', this is the Shin-Bashira.
ALL WORDS HAVE THEIR OWN PAGODAS, when (as here) the pagoda is 5 tiers high then the subtiers are 1+2+3+4+5=5*(1+5)/2=15, as it follows:
1st tier - the Pagoda word;
2nd tier - a 2-gram with one word at the right;
3rd tier - a 2-gram with one word at the left;
4th tier - a 3-gram with two words at the right;
5th tier - a 3-gram with one word at both sides;
6th tier - a 3-gram with two words at the left;
...
Also, the numbers are the occurrences, they are sorted in descdending order.
For big texts, the structure is usually millions of lines high.
.
=======================================================================
Q: How do we view a WRAPPED verison of the file being viewed currently?
=======================================================================
A: Since revision 4, pressing 'Double-Left-Control' (in WRAP mode) will create a file with the same name but also postfixed with the number of columns defining the wrapping.
If the WRAPPED file misses some lines (due to their unwrappability) then Zenless-Zone-Zero Nicole is talking/screaming in Japanese, :P
In essence, the whole process is in 2 steps, the first already mentioned, the second, running another instance of TriMasakari - the CLIPBOARD is set with the wrapped pathfilename.
```

How to compile?

```
[sanmayce@dzvertcheto Trimasakari_benchmark_r3_sourcecode_ELF_EXE]$ /home/sanmayce/qb64/3.9.1/qb64pe -x -f:ExtraCppFlags="-O3 -ffast-math -msse4.2 -maes" trimasakari.bas
QB64-PE Compiler V3.9.1-UNKNOWN
Beginning C++ output from QB64 code...
[..................................................] 100%
Compiling C++ code into executable...
Output: /dz_WD_SN740/z/Trimasakari_benchmark_r3_sourcecode_ELF_EXE/trimasakari
```

The QB64PE compiler is at:  
https://github.com/QB64-Phoenix-Edition/QB64pe/releases/
