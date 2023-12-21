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

This is a short description of Trimasakari revision 3- - the QB64 smooth scrolling file viewer. 
In the package, ELF/EXE binaries are included, full sourcecode as well. 
Trimasakari is an 100% free Smooth Scroll File Walker for Windows/Linux (and Mac, no binary inhere, though). 
.
The central idea is to have a simplistic GUI allowing viewing a given file in three modes:
- WRAP (actually, truncated to a fixed length) mode #1: ASCII field, its HEX equivalent field, the OFFSET (from the start) field; 
- WRAP (actually, truncated to a fixed length) mode #2: Widened ASCII field, the OFFSET (from the start) field;
- RAW mode: Showing logical lines as physical ones, that is, each screen line is a [CR]LF line, i.e. non-wrapped and non-truncated;
.
Switching between the two WRAP modes happens with 'Backspace';
Switching between any of the WRAP modes and RAW mode happens with 'Double-Left-Shift' or Right-Mouse-Button.
.
A quick question:
How do you read the "environment" i.e. (surrounding text) of a found needle into a haystack?
In other words, with assistance of what tool/editor, do you read the paragraphs within (e.g. Wikipedia XML dump, currently a single file 90+GB in size) containing the search pattern "metal fatigue"?
.
As lacking as it may sound, the reality is there is no proper tool giving the Context (the environment) of the found Needles/Patterns.
The mere reporting of line numbers or the logical lines where the Needles/Patterns are found is not enough, many times one wants to EXPLORE what is around them.
.
Quick keyboard input: 
- Use 'Escape' to exit; 
- Use 'Alt+Enter' or 'Double-Left-Alt' to toggle fullscreen/window mode; 
- Use 'Double-Left-Control' to get basic statistics for the current file, as number of lines/words and some more;
- Use 'Double-Left-Shift' to toggle WRAP/RAW mode, WRAP is a forced one i.e. a truncator, whereas RAW shows logical lines as physical lines;
- Use 'Backspace' to toggle short/wide text field; 
- Use 'Home/End/PageUp/PageDown' for going to top/end of file; 
- Use 'Left/Right' to select a preset color (out of 256); 
- Use 'Up/Down' to Smooth-Scroll one line; 
- Use 'Spacebar' to run/pause Automatic-Smooth-Scroll downwards; 
- Use 'Control+Up/Down' to set brightness for current color; 
- Use 'F' to change font; 
- Use 'Enter' to toggle inverse line (auto-hidden when the page is scrolled), when active then search sequence is allowed; 
- Use SLASH i.e. '/' (when inverse line is active) to enter editing current line mode, the resultant string is the Needle i.e. the search pattern, use 'Right-Shift' release to start searching;
- Use 'F3' (release) or 'Double-Right-Shift' (when inverse line is active) to start searching in Wildcard Case-Insensitive Mode, ('*' and '#' wildcards allowed) - the hit could span two lines i.e. there will be no hit misses;
- Use 'Left-Shift' + 'Up/Down' to Rough-Scroll one line, in WRAP mode if mouse pointer is within last 17 columns then a Vertical-Scroll-Bar (unclickable, yet) appears;
.
Quick mouse input: 
- Use 'Left Button Click' to underscore the line under the pointer; 
- Use 'Right Button Click' to toggle WRAP/RAW mode, WRAP is a forced one i.e. a truncator, whereas RAW shows logical lines as physical lines, same as 'Double-Left-Shift';
- Use 'Up/Down Wheel' to Smooth-Scroll one line, same as 'Up/Down'; 
- Use 'Mouse Button #3' to toggle inverse line (auto-hidden when the page is scrolled), when active then search sequence is allowed, same as 'Enter'.
.
Quick Notes: 
Note #0: Resizable (at run-time) window, e.g. it allows your own 4K (a.k.a. UHD a.k.a. QFHD) canvas with size up to (2x236)columns x (2x29)rows.
Note #1: Both {Command-line parameter} and {Drag-n-Drop a file over the icon/launcher} have precedence over clipboard method (Note #2) of accepting. 
Note #2: If the clipboard houses a valid [path]filename - it will be shown, the file being shown can be terabytes in size, the scroll needs only a 'frame'. 
Note #3: There is a bug that is a feature, change the color e.g. with two Right Arrows to #044 and scroll with inversed line in order to highlight desired lines, the bug (of not refreshing the whole page) comes in handy. 
Note #4: Running without a valid [path]filename in the clipboard the tool runs as a color/scroll benchmark, in HD mode. 
Note #5: If e.g. you press Control+C in Caja (Linux Fedora) on selected file - the full path to that file goes to clipboard, then just run Trimasakari - it will show the content of this file (in streaming mode). 
Note #6: The main feature is the easy on the eyes line-by-line smooth scroll, on i5-7200U CPU the scroll speed is 174 FPS for 236Cx29L, just press Spacebar to run/pause scrolling - handy to place your palm resting before the laptop touchpad. 
Note #7: With the cheapest/palest HD screens, the default 8x32 font is [a] candy to the eyes, on fancy wide angles screens it is posssible to tilt the screen to 45 degrees without straining your eyes - the slenderness of font compensates. 
Note #8: In next revisions will add searchability (taken from my Dirwalker tool), the idea is to browse Wikipedia XML dump, EZ! 
Note #9: Currently, Trimasakari is aware of five video modes: 1] 1366x768 (HD ready) with 170columns x 21rows 2] 1280x1024 (SuperXGA) with 158columns x 29rows 3] 1080x1920 (rotated FHD) with 134columns x 56rows 4] 1920x1080 (FHD) with 236columns x 29rows; 5] 1920x1080 (QFHD,4K) with 2x236columns x 2x29rows;
Note #A: Every 2 minutes a powersaving mode is activated, it is meant to save laptop's battery, a known issue is the delayed powering up via a mouse wheel/click, keyboard is okay, though.
.
To-do list:
- Lateral scrolling;
- Accepting only paths (along with [path]filenames) as input, thus showing the directory content, to be mostly a rewritten 'Dirwalker'.
.
Enfun! 
.
2023-December-20
.
Machinely yours,
Sanmaitze
```
