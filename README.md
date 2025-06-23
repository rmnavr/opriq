
<!-- Intro ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# OPRIQ (OPtional RIght Qwerty)

![2 main layers of OPRIQ layout](https://github.com/rmnavr/opriq/blob/main/Docs/Intro.png?raw=true)

---

OPRIQ is keyboard layout with following capabilities:
* **FULL left-handed typing support** via **layers**, **double-function keys** and minimum number of **chords**:
  > Any combination of keys is possible to press with one hand, including:
  > enter/BS, numbers, arrows, F1..F12, etc. plus any combination of Alt/Ctrl/Shift/Win.
  > OK, some tricky hotkeys (like `Win+Alt+Space+5` which sends `Win+Alt+0`) require quite a finger stretching,
  > although can't imagine workflow where such hotkeys are used intensively.
* **Two-handed typing as usual** meaning left-handed typing does not criple usual two-handed typing
  > OPRIQ also has dedicated 2-handed mode, in which 1-handed features that might interfere with speed typing (layers and chords) are turned off.
  > I actually only use it in gaming though.
* **Does not require any additional non-standard hardware** (just a normal ANSI/ISO-keyboard is needed)
* **Introduces only minor changes to QWERTY layout** (relearning should be a breeze)

Requirements:
* Standard ANSI/ISO-keyboard 
* Ideally keyboard that has 6NKRO support (Anti-ghosting)
  > Without it some tricky key combinations (like Alt+Shift+Space+Q) might not work depending on keyboard,
  > still 95% of key combination will work, and remaining 5% will still be pressable with two hands as usual
* OPRIQ works on [AutoHotKey v2.0](https://www.autohotkey.com/), so **only Windows is supported** (for now?)

My personal OPRIQ story:
* OPRIQ development took 8 years (2013-2021) with rigorous battle-testing of 5 vastly different layout iterations each built from scratch
  (including complete relearning of typing for each iteration)
* My current typing speed in OPRIQ is (normal/record): 90/110 wpm two-handed, 50/75 wpm one-handed
* I use OPRIQ mainly for CAD work: entering hotkeys with left hand, mousing with right hand
* Since 2021 I type only in OPRIQ and consider it to be my endgame layout

<!-- __________________________________________________________________________/ }}}1 -->

---

Table of Contents:
- [Detailed layout description](#Detailed-layout-description)
- [Configuration and usage](#Configuration-and-usage)
- [Known Issues](#Known-Issues)
- [Installation](#Installation)

<!-- Description ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Detailed layout description

layers\...

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Config ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Configuration and usage

LCtrl + ...

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Issues ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Known Issues

Currently sometimes (like few times during a work day) below issues occur.

## RAlt sometimes sends Alt (along with opening Nav layer)

Holding RAlt (which supposed to open Navigation layer), sometimes also sends original RAlt key.

RAlt (AltGr) is notorious for creating problems in AutoHotKey.
So the only solution I came up with is remapping RAlt to F14 on register level via Sharpkeys or similar software.
OPRIQ will recognize F14 accordingly.

## CAPS Lock sometimes fires unwantedly (instead of LCtrl)

Same issue as with RAlt. Same solution also: remap CAPS to F13 via Sharpkeys or similar software.
OPRIQ will recognize F13 accordingly.

## Shift sometimes sticks

Entering letters with Shift sometimes 
I am working on this issue. It should be solvable on AutoHotKey level.

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Second language support ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Second language support

ru-lang, ZHGIEZH

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Install ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Installation

1. Install [AutoHotKey v2.0](https://www.autohotkey.com/)
2. Double-click OPRIQ.ahk2 (or open it with AutoHotKey64.exe if *.ahk2 file extension was not recognized automatically)
3. You'll see OPRIQ tray icon, indicating it is now working

<!-- __________________________________________________________________________/ }}}1 -->

