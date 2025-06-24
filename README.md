
<!-- Intro (+ TOC) ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

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

OPRIQ shines when working in hotkey-heavy software like Photoshop, various CADs and similar.

It is built on [AutoHotKey v2.0](https://www.autohotkey.com/) and currently works only on Windows.

Table of Contents:
- [Demonstrations](#Demonstrations)
- [How it works](#How-it-works)
- [TFNJ Variation](#TFNJ-Variation)
- [Second language support](#Second-language-support)
- [Known Issues](#Known-Issues)
- [Requirements](#Requirements)
- [Installation](#Installation)

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Demo ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Demonstrations

Standard ANSI-keyboards are used in videos below. Key-caps are colored for better layout visibility.

*On the fly switch between left-handed and 2-handed typing:*

[![OPRIQ 1h/2h-typing](https://github.com/rmnavr/opriq/blob/main/Docs/2h_switch.png?raw=true)](https://ravrlab.ru/csblog/opriq/files/opriq_1h2h.mp4)

*1-handed coding with OPRIQ layout:*

[![OPRIQ 1-handed coding](https://github.com/rmnavr/opriq/blob/main/Docs/1h_coding.png?raw=true)](https://ravrlab.ru/csblog/opriq/files/opriq_coding.mp4)

My current (2025) typing speeds in OPRIQ (normal/record):
* 95/115 wpm two-handed
* 55/75 wpm one-handed text
* ~40 wpm one-handed coding

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
* 3 **chords** (simultaneous key presses) for left hand at home row that enable entering `BS`/`Enter`/`Delete`
  keys from `HOME` layer. Modifiers (Alt/Ctrl/Shift) work with chords too.
  > In the long run I found chords to be less crippling on the left hand than reaching to `BS`/`Enter`/`Delete`
  > from `NAVIGATION` layer.
* Pressing any of right-handed keys will disable `SPACE`/`TAB` from their layer-changing features,
  and will also disable **chords** — all of that **for a timer of 1 second**
  (`RAlt` will still be able to open `NAVIGATION` layer though).
  You can see if timer is active via GUI (described further).
  > Timer feature becomes crucial once you exceed 60 wpm two-handed typing speed.
  > Thanks to this timer, when you are speed-typing, you will not need to worry about accidentally
  > holding `Space` for too long (thus unwantedly opening `TEXT2` layer) and things like that.

Alt+TAB has a special recognition:
* If you hold `LAlt` before pressing `TAB`, standard Alt+TAB windows feature will activate without delay
* You should press `TAB` BEFORE holding `LAlt` if you want reach `NAVIGATION` layer (when you aim to press `LAlt+Home` or smth)

## MODE ONLY2H (compatibility mode)

Games (or other software) that require holding `TAB`/`Space`/`S`/`D`/`T` might work bad with OPRIQ.
`TAB`/`Space` will open layers, `S`/`D`/`T` will send chords if pressed simultaneously.
In most games this is not what you want.

For such a case you can use `ONLY2H` mode, in which keyboard has no one-handed features (it's chords and layers),
although it keeps it's main layout. You'll still have `NAVIGATION` layer reachable through `RAlt`,
and `CNFG` layer as usual.

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/Docs/ONLY2H.png?raw=true" alt="MODE ONLY2H" />
</p>

> BTW, in programming games like Shapez 2, Turing Complete, etc. 
> opening layers and sending chords may be exactly what you want — so `1L2H` mode will work great there.

## Configuration layer

Hold `LCtrl` (usually placed at bottom left key of keyboard) to open `CNFG` layer.

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/Docs/CNFG.png?raw=true" alt="LAYER CNFG" />
</p>

You can do all sorts of things in `CNFG` layer including:
* `LCtrl + 1` switches to `1L2H` mode, `LCtrl + 2` switches to `ONLY2H` mode
* `LCtrl + s` **suspends** and `LCtrl + a` **activate** OPRIQ app. Suspend deactivates all hotkeys except Suspend/Activate/Reload commands on `CNFG` layer.
* `LCtrl + tilde` **reloads** OPRIQ. Use it when smth is stuck.
* `LCtrl + c` acts as **CAPS Lock** key (you might require it for unstucking unwanted CAPS, see [Known Issues](#Known-Issues))
* `LCtrl + g` activates **mini-GUI** window — it will indicate active mode (`1L2H` or `ONLY2H`) and for `1L2H` will also show
  if 2-handed-timer is active (indicating that 1L-features are suppresed for ~1 second).
  Try reloading App if GUI is not visible (it will place itself on top of all windows).

<!-- __________________________________________________________________________/ }}}1 -->
<!-- TFNJ ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# TFNJ Variation

**By default, variation described below is turned off, because I don't think it fits well for general user.**

I personally use OPRIQ with T/F and N/J keys swapped (because T and N are much more frequent than F and J).
This change is accordingly propagated to all modes/layers/chords.
In demo videos I use this TFNJ version. It makes left index finder life noticeably easier for left-handed typing.

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/Docs/TFNJ.png?raw=true" alt="TFNJ variation" />
</p>

If you want to try it, then edit `OPRIQ.ahk2` source code and change this line (in the beginning of the file):
```ahk
activate_TFNJ := False
```
to this:
```ahk
activate_TFNJ := True
```

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Second language support ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Second language support

ru-lang, ZHGIEZH

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Issues ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Known Issues

## Limitations

* OPRIQ does not work in Windows log-in screen. Treat your keyboard as normal QWERTY in this case.
* Some protected forms in internet browsers (like finance-related) will process keyboard keys as if OPRIQ is not running
* Working with remote devices might be challenging. Sometimes OPRIQ on your local machine will be able to send correct keys to remote device.
  Sometimes it is better to run OPRIQ directly on remote machine. I think it heavily depends on type of remote connection.

> Changing source language to smth like C++/Rust, or building QMK version of OPRIQ might solve those issues.
> I don't plan to implement any of that though.

## AutoHotKey issues (solved with compromise)

Few times during a work day below issues might occur:
* Holding `RAlt` (which supposed to only open `NAVIGATION` layer), sometimes also sends original `RAlt` key. Any subsequent key presses work as usual.
* `CAPS` sometimes fires unwantedly (instead of acting as `LCtrl`)

`RAlt` (AltGr) and `CAPS` are notorious for creating problems in AutoHotKey.
The only decent solution I came up with is **performing some minimal remappings on register level** via Sharpkeys or similar software.
Make remaps shown on the picture, and OPRIQ will recognize F13/F14/F15 accordingly.
Be aware that you'll loose your original CAPS/LCtrl/RAlt though (when keyboard is used without OPRIQ).

> When using Sharpkeys, you can load binary file [for_Sharpkeys/opriq_ff_remaps.skl](for_Sharpkeys/opriq_ff_remaps.skl) with preconfiged remaps.

<p align="center">
<img src="https://github.com/rmnavr/opriq/blob/main/for_Sharpkeys/FF_remaps.png?raw=true" alt="Remaps for Sharpkeys" />
</p>

**These remappings are NOT absolutely required. Especially if issues above do not irritate you that much.**

## Bugs

There are 2 known bugs which I am trying to solve. Their frequency is like 1..2 times during a work day.
* Entering letters with `Shift` sometimes holds `Shift` pressed.
  When it happens, just press left and right `Shift` (not necessarily at the same time) and it will unstuck.
* In `ONLY2H` mode, chording keys might stuck (although there are no chords in `ONLY2H`). Press key again and it will unstuck.

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Requirements ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Requirements

Software:
* OPRIQ works on [AutoHotKey v2.0](https://www.autohotkey.com/), so **only Windows is supported** 
  > OPRIQ idea can be implemented on QMK, on Linux, Mac, etc. I currently don't have plans of doing it myself though.
* OPRIQ needs to be launched when **standard english QWERTY layout** is currently selected in the system

Hardware:
* You'll need **standard ANSI/ISO-keyboard** (all docs are made for ANSI keyboard, however changes to ISO should be obvious)
* Ideally keyboard should have **6NKRO support** (anti-ghosting), although not obligatory
  > Without 6NKRO some tricky key combinations (like `Alt+Shift+Space+Q`) might not work depending on keyboard.
  > Still 99% of any reasonable key combination will probably work, and remaining 1% will be pressable with two hands as usual.
  > 
  > However for best learning experience it is better to use 6NKRO (because in some unexpected behaviour you'll be sure it is not hardware to blame).

<!-- __________________________________________________________________________/ }}}1 -->
<!-- Install ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\ {{{1 -->

# Installation

There 2 ways to launch OPRIQ.

> For both those options if you want to completely get rid of [RAlt and CAPS Lock issues](#Known-Issues),
> make remaps (descriped in that chapter) at register level. It is not required though.

## Without installing AutoHotKey (simplier way)

1. Download `OPRIQ.exe`, `OPRIQ_01.png` and `OPRIQ_02.png` to some folder.
2. Make sure your active layout is QWERTY (if it's not, some keys might not work).
3. Run `OPRIQ.exe`.
4. You'll see OPRIQ icon in tray indicating it is now working.

## With AutoHotKey

Choose this option if you want to run modified OPRIQ code.

1. Install [AutoHotKey v2.0](https://www.autohotkey.com/)
2. Download `OPRIQ.ahk2`, `OPRIQ_01.png` and `OPRIQ_02.png` to some folder.
3. Make sure your active layout is QWERTY (if it's not, some keys might not work).
4. Double-click `OPRIQ.ahk2` (or open it with `AutoHotKey64.exe` if `*.ahk2` file extension was not recognized automatically)
5. You'll see OPRIQ icon in tray indicating it is now working.

<!-- __________________________________________________________________________/ }}}1 -->

