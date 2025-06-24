
<!-- Intro + TOC ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# OPRIQ (OPtional RIght Qwerty)

OPRIQ is keyboard layout with possibility of solo-left-handed-typing of any possible keys combinations
(you can even code with just left hand).
Solo-left-handed-typing does not prevent two-handed typing in any way.
OPRIQ doesn't require any special keyboard, and builds on standard QWERTY layout
(so learning it should be a breeze).

> OPRIQ development took 8 years (2013-2021) with rigorous testing of 5 vastly
> different layout iterations each built from scratch
> (including building hardware prototypes and complete relearning of typing for each iteration).
> Most of those iterations were also very far from QWERTY layout.
> Point is: **to a smallest single little detail OPRIQ was
> forged in battle and can stand by it's design decisions**.

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/Docs/Intro.png?raw=true" alt="OPRIQ Home Layer" />
</p>

OPRIQ works best with hotkey-heavy software like Photoshop, various CADs and similar.
It is built on [AutoHotKey v2.0](https://www.autohotkey.com/) and currently works only on Windows.

Table of Contents:
- [Demonstrations](#Demonstrations)
- [Overview](#Overview)
- [Detailed layout description](#Detailed-layout-description)
- [Configuration and usage](#Configuration-and-usage)
- [Variations](#Variations)
- [Second language support](#Second-language-support)
- [Known Issues](#Known-Issues)
- [Known Limitations](#Known-Limitations)
- [Installation](#Installation)

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Demo ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Demonstrations

Standard ANSI-keyboards are used in videos below. Key-caps are colored for better layout visibility.

*On the fly switch between left-handed and 2-handed typing:*

[![OPRIQ 1h/2h-typing](https://github.com/rmnavr/opriq/blob/main/Docs/2h_switch.png?raw=true)](https://ravrlab.ru/csblog/opriq/files/opriq_1h2h.mp4)

*1-handed coding with OPRIQ layout:*

[![OPRIQ 1-handed coding](https://github.com/rmnavr/opriq/blob/main/Docs/1h_coding.png?raw=true)](https://ravrlab.ru/csblog/opriq/files/opriq_coding.mp4)

<!-- __________________________________________________________________________/ }}}1 -->
<!-- How it works ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# How it works

> You can find all the schemes shown in this chapter in original excel `Docs/OPRIQ.xlsx` file

OPRIQ has 2 distinct modes:
* `1L2H` — main mode, you can type both with solo-left hand or with both hands
  > Naming `1L2H` is a shorthand for phrase "solo-left-handed OR two-handed"
* `ONLY2H` — compatibility mode for games and software that respond bad to 1L2H mode; it simply
  switches off all 1L-features of OPRIQ

You can switch between modes via `CNFG` layer (reachable through original `LCtrl` key, more on that below).
OPRIQ tray icon will change accordingly.

## MODE 1L2H (main mode)

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/Docs/1L2H.png?raw=true" alt="MODE 1L2H" />
</p>

`1L2H` mode builds on several things:
* 3 main **layers**:
  * `HOME`
  * `TEXT2` (hold `Space` to reach it)
  * `NAVIGATION` (hold `TAB` or `RAlt` to reach it)
  > Also there is `TEXT2ALT` layer (reached by holding both `TAB` and `Space`),
  > but it is just a `TEXT2` with all keys seen as if `LAlt` is pressed.
  > This layer enables user to send `LAlt`-modified keys, while user's thumb is already busy with `Space` key.
* 3 **chords** (simultaneous key presses) at home row that enable entering `BS`/`Enter`/`Delete`
  keys from `HOME` layer. Modifiers (Alt/Ctrl/Shift) work with chords too.
  > In the long run I found chords to be less crippling on the left hand than reaching to `BS`/`Enter`/`Delete`
  > from `NAVIGATION` layer.
* Pressing any of right-handed keys will disable `SPACE`/`TAB` from their layer-changing features,
  and will also disable **chords** — all of that **for a timer of 1 second**
  (`RAlt` will still be able to open `NAVIGATION` layer though).
  You can see if timer is active via GUI (described further).
  > Timer feature becomes crucial once you exceed 60 wpm two-handed typing speed.
  > Due to this timer, when you are speed-typing, you will not need to worry about accidentally
  > holding `Space` for too long (thus unwantedly opening `TEXT2` layer) and things like that.

Alt+TAB has a special recognition:
* If you hold `LAlt` before pressing `TAB`, standard Alt+TAB windows feature will activate without delay
* You should press `TAB` BEFORE holding `LAlt` if you want reach `NAVIGATION` layer (when you aim to press `LAlt+Home` or smth)

## MODE ONLY2H (compatibility mode)

Games (or other software) that require holding `TAB`/`Space`/`S`/`D`/`T` might work bad with OPRIQ.
`TAB`/`Space` will open layers, `S`/`D`/`T` will send chords if pressed simultaneously.
Im most games this is not what you want.

For such a case you can use `ONLY2H` mode, in which keyboard has no one-handed features (it's chords and layers),
although it keeps it's main layout. You'll still have `NAVIGATION` layer reachable through `RAlt`,
and `CNFG` layer as usual.

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/Docs/ONLY2H.png?raw=true" alt="MODE ONLY2H" />
</p>

> BTW, in programming games like Shapez 2, Turing Complete, etc. 
> opening layers and sending chords may be exactly what you want — so `1L2H` mode will work great there.

## Configuration layer

Hold `LCtrl` (bottom left key of keyboard) to open `CNFG` layer.

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/Docs/CNFG.png?raw=true" alt="LAYER CNFG" />
</p>

You can do all sorts of things in `CNFG` layer including:
* Suspend (deactivate all hotkeys except `CNFG` layer) and Activate app
* Switch modes: `1L2H` <-> `ONLY2H`
* Activate CAPS Lock (including for unstucking it, see [Known Issues](#Known-Issues))
* Activate mini-GUI — it will indicate active mode (`1L2H` or `ONLY2H`) and for `1L2H` will also show
  if 2-handed-timer is active (indicating that 1L-features are suppresed for ~1 second) 

<!-- __________________________________________________________________________/ }}}1 -->


<!-- Overview ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Overview

OPRIQ is keyboard layout with following capabilities:
* Killer-feature of OPRIQ is **full left-handed typing support** via **layers**, **double-function keys**,
  **duplication of modifiers keys** and minimum number of **chords**.
  > "Full left-handed typing support" means that **ANY combination of keys is possible to press with one hand** including:
  > symbols, numbers, arrows, F1..F12, etc. plus any combination of Alt/Ctrl/Shift/Win.
  > OK, some tricky hotkeys (like `Win+Alt+Space+5` which sends `Win+Alt+0`) require quite a finger stretch,
  > although can't imagine workflow where such hotkeys are used intensively.
* **Left-handed typing does not criple usual two-handed typing**, which is achieved via short **2-handed-timer**
* **Dedicated 2-handed mode** in which 1-handed features that might interfere with speed typing (layers and chords) are completely turned off.
  Do not confuse it with normal OPRIQ mode, in which 2-handed typing works too (via aforementioned 2-handed-timer).
  > In my experience, the need to use dedicated 2h-mode arises only in gaming.
* **Does not require any non-standard keyboard** (just a normal membrane ANSI/ISO-keyboard is enough)
* **Introduces only minor changes to QWERTY layout** (relearning should be a breeze)

Requirements:
* **Standard ANSI/ISO-keyboard**
* Ideally keyboard that has **6NKRO support** (anti-ghosting), although not obligatory
  > Without 6NKRO some tricky key combinations (like `Alt+Shift+Space+Q`) might not work depending on keyboard,
  > still 95% of key combination will work, and remaining 5% will still be pressable with two hands as usual.
  > 
  > See 1h-coding demo video above — I use cheap membrane keyboard there and experience no problems.
  > Still, this keyboard choked on some other rare (not used in video) key combinations.
* OPRIQ works on [AutoHotKey v2.0](https://www.autohotkey.com/), so **only Windows is supported** 
  > OPRIQ idea can be implemented on QMK, on Linux, Mac, etc. I currently don't have plans of doing it myself though.
* OPRIQ builds from **standard english QWERTY layout** 


<!-- __________________________________________________________________________/ }}}1 -->

<!-- Config and usage ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Configuration and usage

LCtrl + ...

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Variations ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Variations

OPRIQ comes in 2 variations:
* `OPRIQ_Base.ahk2` — OPRIQ based on normal QWERTY
* `OPRIQ_TFNJ.ahk2` — the only changes are that `T` is swapped with `F`, and `N` is swapped with `J`
  (meaning `N` and `T` are placed at home row since they are much more frequent than `F` and `J`)

I personally use TFNJ, since Base version somewhat cripples index finger in one-handed typing.
However I recommend trying Base version first to see if OPRIQ overall works for you (it requires minimal relearning from standard QWERTY).

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Second language support ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Second language support

ru-lang, ZHGIEZH

<!-- __________________________________________________________________________/ }}}1 -->

<!-- Issues ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Known Issues

Currently sometimes (like few times during a work day) below issues occur.

## RAlt sometimes sends Alt (along with opening Nav layer)

Holding RAlt (which supposed to only open Navigation layer), sometimes also sends original RAlt key. Any subsequent key presses work as usual.

RAlt (AltGr) is notorious for creating problems in AutoHotKey.
So the only solution I came up with is **remapping RAlt to F14 on register level** via Sharpkeys or similar software.
OPRIQ will recognize F14 accordingly.

## CAPS Lock sometimes fires unwantedly (instead of LCtrl)

Same issue as with RAlt. Same solution also: **remap CAPS to F13** via Sharpkeys or similar software.
OPRIQ will recognize F13 accordingly.

## Shift sometimes sticks

Entering letters with Shift sometimes holds Shift pressed. When it happens, just press left and right Shifts (not necessarily at the same time) and it will unstuck.

*I am working on this issue. It should be solvable at AutoHotKey level.*

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Limitations ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Known Limitations

Desktop usage:
* OPRIQ does not work in Windows log-in screen. Treat your keyboard as normal QWERTY in this case.
* Some protected forms in internet browsers (like finance-related) will process keyboard keys as if OPRIQ is not running
* Working with remote devices:
  * Sometimes OPRIQ on your local machine will be able to send correct keys to remote device. Sometimes not.
  * Sometimes running OPRIQ direclty on remote machine will solve the issue. Sometimes not.

Hardware limitations:
* On keyboards without 6NKRO some tricky key combinations won't be recognized (in all the membrane keyboards I used it usually were some obscure seldomly used hotkeys).
  You still can enter those keys normally via 2 hands.
* If you use DVORAK or other non-QWERTY layout, OPRIQ will not work correctly

Not all games support 1h-mode properly:
* One-shot keys usually work without problems (great for CAD-like games like Shapez 2 or Turing Complete)
* Letter/number-keys that require holding double-function or chording keys will produce unwanted result:
  * for example, `Space` (usually working as jump in games) will not have "hold Space for longer jump" capability
  * another example is holding `s+d` (usually working as "move down left" in games) — it might send chord for `BS`, which is usually not what you want
* Anyway, **dedicated 2h-mode** solves all aformentioned gaming issues

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Install ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Installation

1. Install [AutoHotKey v2.0](https://www.autohotkey.com/)
2. If you want to completely get rid of [RALt and CAPS Lock issues](#Known-Issues),
   remap at register level `RAlt` to `F14` and `CAPS` to `F13` via Sharpkeys or similar software.
3. Download OPRIQ.ahk2 to your PC and double-click it (or open it with AutoHotKey64.exe if *.ahk2 file extension was not recognized automatically)
4. You'll see OPRIQ tray icon, indicating it is now working

<!-- __________________________________________________________________________/ }}}1 -->

# My personal remarks on OPRIQ

* Since 2021 I type only in OPRIQ and consider it to be my endgame layout. 
  I don't plan on changing any of core OPRIQ ideas or developing new layout.
* My current typing speed in OPRIQ is (normal/record): 95/115 wpm two-handed, 55/75 wpm one-handed
* I use OPRIQ mainly for CAD work: entering hotkeys with left hand, mousing with right hand
* No, I normaly don't use OPRIQ for one-handed coding, I use 2 hands for coding like a sane person

