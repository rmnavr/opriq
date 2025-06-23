
<!-- Intro + Demos ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# OPRIQ (OPtional RIght Qwerty)

![2 main layers of OPRIQ layout](https://github.com/rmnavr/opriq/blob/main/Docs/Intro.png?raw=true)

OPRIQ is keyboard layout with possibility of solo-left-handed-typing of any possible keys combinations. You can even code with only left hand.
Normal 2-handed-typing works too (and it does NOT require tedious mode-switch).

Table of Contents:
- [Demonstrations](#Demonstrations)
- [Overview](#Overview)
- [Detailed layout description](#Detailed-layout-description)
- [Configuration and usage](#Configuration-and-usage)
- [Known Issues](#Known-Issues)
- [Installation](#Installation)

# Demonstrations

On the fly switch between left-handed and 2-handed typing:

[![OPRIQ 1h/2h-typing](https://github.com/rmnavr/opriq/blob/main/Docs/2h_switch.png?raw=true)](https://ravrlab.ru/csblog/opriq/files/opriq_1h2h.mp4)

1-handed coding with OPRIQ layout:

[![OPRIQ 1-handed coding](https://github.com/rmnavr/opriq/blob/main/Docs/1h_coding.png?raw=true)](https://ravrlab.ru/csblog/opriq/files/opriq_coding.mp4)

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Overview ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Overview

OPRIQ is keyboard layout with following capabilities:
* Killer-feature of OPRIQ is **FULL left-handed typing support** via **layers**, **double-function keys** and minimum number of **chords**.
  > **FULL** left-handed typing support means that **ANY combination of keys is possible to press with one hand**, including:
  > symbols, numbers, arrows, F1..F12, etc. plus any combination of Alt/Ctrl/Shift/Win.
  > OK, some tricky hotkeys (like `Win+Alt+Space+5` which sends `Win+Alt+0`) require quite a finger stretch,
  > although can't imagine workflow where such hotkeys are used intensively.
* **Left-handed typing does not criple usual two-handed typing**, which is achieved via short **2-handed-timer**
* **Dedicated 2-handed mode** in which 1-handed features that might interfere with speed typing (layers and chords) are completely turned off.
  Do not confuse it with normal OPRIQ mode, in which 2-handed typing works too (via aforementioned 2-handed-timer).
  > I actually only use it in gaming though.
* **Does not require any additional non-standard hardware** (just a normal ANSI/ISO-keyboard is needed)
* **Introduces only minor changes to QWERTY layout** (relearning should be a breeze)

Requirements:
* Standard ANSI/ISO-keyboard 
* Ideally keyboard that has 6NKRO support (Anti-ghosting)
  > Without it some tricky key combinations (like `Alt+Shift+Space+Q`) might not work depending on keyboard,
  > still 95% of key combination will work, and remaining 5% will still be pressable with two hands as usual
* OPRIQ works on [AutoHotKey v2.0](https://www.autohotkey.com/), so **only Windows is supported** (for now?)

My personal OPRIQ story:
* OPRIQ development took 8 years (2013-2021) with rigorous battle-testing of 5 vastly different layout iterations each built from scratch
  (including complete relearning of typing for each iteration)
* My current typing speed in OPRIQ is (normal/record): 90/110 wpm two-handed, 50/75 wpm one-handed
* I use OPRIQ mainly for CAD work: entering hotkeys with left hand, mousing with right hand
* Since 2021 I type only in OPRIQ and consider it to be my endgame layout
* No, I normaly don't use OPRIQ for one-handed coding, I use 2 hands for coding like a sane person

<!-- __________________________________________________________________________/ }}}1 -->

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

