# POK3R keyboard setup

Here are notes on how to program your Pok3r VTG-6100 keyboard.

You will find general instructions first and then more specific recipies after that.

## General

First understand how to reset everything to default, for the mess you'll make
the first few times

| Action                    | Key dance                                                            |
| ---                       | ---                                                                  |
| Factory reset             | Hold both the left and right <kbd>ALT</kbd> keys                     |
| Reset selected layer only | <kbd>FN</kbd> + <kbd>R</kbd> until LED under spacebar stops flashing |

The [POK3R User Manual](files\POK3R.User.Manual.V1.5.pdf) tells all, below is
a reflow of that and the original [David Jeni
repo](https://github.com/davidjenni/pok3r-layouts) this repo was forked from. Review
those if anything here is wrong or unclear. Also submit a PR, that would be
appreciated.

## Switching Layers

The LED color signals the current key layer. The keys on the key dance are
those printed on the key on top

| Layer   | Color  | Key dance                  |
| ---     | ---    | ---                        |
| Layer 1 |        | <kbd>FN</kbd>+<kbd>M</kbd> |
| Layer 2 | bue    | <kbd>FN</kbd>+<kbd><</kbd> |
| Layer 3 | red    | <kbd>FN</kbd>+<kbd>></kbd> |
| Layer 4 | purple | <kbd>FN</kbd>+<kbd>?</kbd> |


## Programming of layers

The default layer cannot be programmed. During programming, use the keys as
labelled on the keyboard, irrespective of any reassignments.

The general recipe is as follows:

| Step | Key Dance                        | Notes                                                              | Visual Feedback                         |
| ---- | ---------                        | ------                                                             | ----------------                        |
| 1    | <kbd>FN</kbd> + R<kbd>Ctrl</kbd> | Use L<kbd>CTRL</kbd> if <kbd>FN</kbd> has been reassigned already. | Second LED under space bar is now lit   |
| 2    | <kbd>target key</kbd>            |                                                                    |                                         |
| 3    | <kbd>new content</kbd>           | can be up to 32 char                                               |                                         |
| 4    | <kbd>PN</kbd>                    |                                                                    | second LED will blink while programming |
| 5    | <kbd>FN</kbd> + R<kbd>CTRL</kbd> | to exit programming                                                | second LED extinguishes                 |

Say I want to map key <kbd>i</kbd> on Layer 2 (Blue) to type my bank password, because
that's such a smart thing to do, I would type the following:

<kbd>FN</kbd> R<kbd>CTRL</kbd> i PlzStealMyMoney <kbd>PN</kbd> <kbd>FN</kbd> + R<kbd>CTRL</kbd>

Now, when Layer 2 is active (The blue led is lit) and I hit <kbd>i</kbd>, the keyboard
types `PlzStealMyMoney`.

Below follows a few remappings that are generally usefull.

## <a name="common_bindings"></a>Common key bindings

I use zsh in vim mode in the terminal, with any PyCharm, spacemancs, and vim.
So I want vim keybindings everywhere. To support this I map:

* <kbd>CAPSLOCK</kbd> to <kbd>CTRL</kbd>
* Map the arrow keys (Printed on the jkli keys) to the standard hjkl keys
* map the <kbd>FN</kbd> key to L<kbd>CTRL</kbd> (bottom leftmost key) to allow arrow keys in things
  Like PyCharm.


### <kbd>CAPSLOCK</kbd> always as <kbd>CTRL</kbd> 

Follow from left to right. Note you can do all the mappings seperated with <kbd>PN</kbd> between and
<kbd>FN</kbd> + R<kbd>CTRL</kbd> at the begining and the end.

| Start                          | Current                           | New Key         | Program       | Stop                          |
| ---                            | ---                               | ---             | ---           | ---                           |
| <kbd>FN</kbd>+R<kbd>CTRL</kbd> | <kbd>CapsLock</kbd>               | <kbd>CTRL</kbd> | <kbd>PN</kbd> | <kbd>FN</kbd>+R<kbd>CTRL<kbd> |
| <kbd>FN</kbd>+R<kbd>CTRL</kbd> | <kbd>FN</kbd>+<kbd>CapsLock</kbd> | <kbd>CTRL</kbd> | <kbd>PN</kbd> | <kbd>FN</kbd>+R<kbd>CTRL<kbd> |

### Home

`FN + I` then: `FN + H` then: `PN`

### Vim HJKL and Page Up/Down

| Movement | Current  | New Key  | Program |
| ---      | ---      | ---      | --      |
| Left     | `FN + H` | `FN + J` | `PN`    |
| Down     | `FN + J` | `FN + K` | `PN`    |
| Up       | `FN + K` | `FN + I` | `PN`    |
| PgDown   | `FN + F` | `FN + O` | `PN`    |
| PgUp     | `FN + B` | `FN + U` | `PN`    |


### Volume controls

| Volume | Current  | New Key   | Program |
| ---    | ---      | ---       | ---     |
| Mute   | `FN + X` | `FN + /?` | `PN`    |
| Vol-   | `FN + C` | `FN + ,<` | `PN`    |
| Vol+   | `FN + V` | `FN + .>` | `PN`    |

## <a name="move_FN"></a>Move FN to L_Ctrl

HJKL as cursor keys are more ergonomical to reach by moving the FN to the left
Ctrl key location. Getting to the ` key is also way easier. Navigating VIM
history and PyCharm intellisence dialogs also works out of the box. ALthough its propably
better to map them to natibe hjkl anyway, if you can.


* Switch to Layer 2 (or 3, 4); this programming is per layer
* Unplug keyboard
* DIP switch 4 to ON
* Plugin keyboard again, then press `FN` then: `L_Ctrl` then: `PN` then: `PN` (to leave it in its original location)
* DIP switch 4 back to OFF (no need to unplug)


## Good OSX Layer (Red)

Below setup is reportedly good vir OSX users. I have not tried it.

`FN + .` to switch to Layer  3

* [Move FN to L_Ctrl](#move_FN)
* `FN + R_Ctrl` to enter programming
* [Common bindings](#common_bindings)
* Swap Cmd/Opt keys on both sides of space bar:
  * L_Cmd: `L_Alt` then: `L_WIN` then: `PN`
  * L_Option: `L_WIN` then: `L_Alt` then: `PN`
  * R_CMD: `R_Alt` then: `R_FN` (Win) then: `PN`
  * R_Option: `R_FN` (Win) then: `R_Alt` then: `PN`
* `FN + R_Ctrl` to exit programming

Resulting programming

![OSX layout](img/layout-osx.png)


## Good Windows layer (Blue)

Below setup is reportedly good vir Windows users. I would not know as I don't
give a rat's arse about Windows, and neither should you.

`FN + ,<` to switch to Layer 2

* [Move FN to L_Ctrl](#Move_FN)
* `FN + R_Ctrl` to enter programming
* [Common bindings](#common_bindings)
* `FN + R_Ctrl` to exit programming

Resulting programming

![Windows layout](img/layout-windows.png)

## Sources

The how-to for these mappings is from 2 reddit threads

* [r/mk: HowTo program pok3r](http://www.reddit.com/r/MechanicalKeyboards/comments/35uy60/guide_howto_program_your_pok3r_programming_layers/)
* [r/mk: HowTo media controls pok3r](http://www.reddit.com/r/MechanicalKeyboards/comments/37j3sx/guide_modification_pok3r_media_volume_controls_hw/)

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.


Windows Layout on [keyboard-layout-editor.com](http://www.keyboard-layout-editor.com/##@_name=Pok3r%20Layer%203%20for%20Windows&author=davidjenni&notes=See%20%5Bgithub%5D(https%2F:%2F%2F%2F%2Fgithub.com%2F%2Fdavidjenni%2F%2Fpok3r-layouts)%3B&@_y:1.5&c=%233c4041&t=%23aba18b&p=DCS&a:5%3B&=%0A%0A%0A%0A%60%20~%0A%0AEsc&_a:4%3B&=!%0A1%0A%0A%0AF1&=%2F@%0A2%0A%0A%0AF2&=%23%0A3%0A%0A%0AF3&=$%0A4%0A%0A%0AF4&=%25%0A5%0A%0A%0AF5&=%5E%0A6%0A%0A%0AF6&=%2F&%0A7%0A%0A%0AF7&=*%0A8%0A%0A%0AF8&=(%0A9%0A%0A%0AF9&=)%0A0%0A%0A%0AF10&=%2F_%0A-%0A%0A%0AF11&=+%0A%2F=%0A%0A%0AF12&_w:2%3B&=%0ABackspace%0A%0A%0ADel%3B&@_w:1.5%3B&=%0ATab&=Q&=W&=E&=R%0A%0A%0A%0AReset&=T%0A%0A%0A%0A15ms&=Y%0A%0A%0A%0ACal&=U%0A%0A%0A%0APgUp&_c=%23c7c3b5&t=%23ba1312%3B&=I%0A%0A%0A%0AHome&_c=%233c4041&t=%23aba18b%3B&=O%0A%0A%0A%0APgDn&=P%0A%0A%0A%0APrtSc&=%7B%0A%5B%0A%0A%0AScrlk&=%7D%0A%5D%0A%0A%0APause&_w:1.5%3B&=%7C%0A%5C%3B&@_c=%23c7c3b5&t=%23ba1312&w:1.25&w2:1.75%3B&=%0ACtrl&_x:0.5&c=%233c4041&t=%23aba18b%3B&=A&=S&=D&_c=%23c7c3b5&t=%23ba1312%3B&=F%0A%0A%0A%0APgDn&_c=%233c4041&t=%23aba18b%3B&=G%0A%0A%0A%0A0.1s&_c=%23c7c3b5&t=%23ba1312%3B&=H%0A%0A%0A%0ALeft&=J%0A%0A%0A%0ADown&=K%0A%0A%0A%0AUp&=L%0A%0A%0A%0ARight&_c=%233c4041&t=%23aba18b%3B&=%2F:%0A%2F%3B%0A%0A%0AIns&=%22%0A'%0A%0A%0ADel&_w:2.25%3B&=%0AEnter%3B&@_w:2.25%3B&=%0AShift&=Z&=X&=C&=V&_c=%23c7c3b5&t=%23ba1312%3B&=B%0A%0A%0A%0APgUp&_c=%233c4041&t=%23aba18b%3B&=N%0A%0A%0A%0AEnd&=M%0A%0A%0A%0ADefault&=%3C%0A,%0A%0A%0ALayer%202&=%3E%0A.%0A%0A%0ALayer%203&=%3F%0A%2F%2F%0A%0A%0ALayer%204&_w:2.75%3B&=%0AShift%3B&@_c=%23c7c3b5&t=%23ba1312&w:1.25%3B&=%0AFN&_c=%233c4041&t=%23aba18b&w:1.25%3B&=%0AWin&_w:1.25%3B&=%0AAlt&_p=DCS%20SPACE&w:6.25%3B&=&_p=DCS&w:1.25%3B&=%0AAlt&_c=%23c7c3b5&t=%23ba1312&w:1.25%3B&=%0AWin&_c=%233c4041&t=%23aba18b&w:1.25%3B&=%0APn&_w:1.25%3B&=%0ACtrl)

OSX Layout on [keyboard-layout-editor.com](http://www.keyboard-layout-editor.com/##@_name=Pok3r%20Layer%203%20for%20OSX%2F%2FMac&author=davidjenni&notes=See%20%5Bgithub%5D(https%2F:%2F%2F%2F%2Fgithub.com%2F%2Fdavidjenni%2F%2Fpok3r-layouts)%3B&@_y:1.5&c=%233c4041&t=%23aba18b&p=DCS&a:5%3B&=%0A%0A%0A%0A%60%20~%0A%0AEsc&_a:4%3B&=!%0A1%0A%0A%0AF1&=%2F@%0A2%0A%0A%0AF2&=%23%0A3%0A%0A%0AF3&=$%0A4%0A%0A%0AF4&=%25%0A5%0A%0A%0AF5&=%5E%0A6%0A%0A%0AF6&=%2F&%0A7%0A%0A%0AF7&=*%0A8%0A%0A%0AF8&=(%0A9%0A%0A%0AF9&=)%0A0%0A%0A%0AF10&=%2F_%0A-%0A%0A%0AF11&=+%0A%2F=%0A%0A%0AF12&_w:2%3B&=%0ABackspace%0A%0A%0ADel%3B&@_w:1.5%3B&=%0ATab&=Q&=W&=E&=R%0A%0A%0A%0AReset&=T%0A%0A%0A%0A15ms&=Y%0A%0A%0A%0ACal&=U%0A%0A%0A%0APgUp&_c=%23c7c3b5&t=%23ba1312%3B&=I%0A%0A%0A%0AHome&_c=%233c4041&t=%23aba18b%3B&=O%0A%0A%0A%0APgDn&=P%0A%0A%0A%0APrtSc&=%7B%0A%5B%0A%0A%0AScrlk&=%7D%0A%5D%0A%0A%0APause&_w:1.5%3B&=%7C%0A%5C%3B&@_c=%23c7c3b5&t=%23ba1312&w:1.25&w2:1.75%3B&=%0ACtrl&_x:0.5&c=%233c4041&t=%23aba18b%3B&=A&=S&=D&_c=%23c7c3b5&t=%23ba1312%3B&=F%0A%0A%0A%0APgDn&_c=%233c4041&t=%23aba18b%3B&=G%0A%0A%0A%0A0.1s&_c=%23c7c3b5&t=%23ba1312%3B&=H%0A%0A%0A%0ALeft&=J%0A%0A%0A%0ADown&=K%0A%0A%0A%0AUp&=L%0A%0A%0A%0ARight&_c=%233c4041&t=%23aba18b%3B&=%2F:%0A%2F%3B%0A%0A%0AIns&=%22%0A'%0A%0A%0ADel&_w:2.25%3B&=%0AEnter%3B&@_w:2.25%3B&=%0AShift&=Z&=X&=C&=V&_c=%23c7c3b5&t=%23ba1312%3B&=B%0A%0A%0A%0APgUp&_c=%233c4041&t=%23aba18b%3B&=N%0A%0A%0A%0AEnd&=M%0A%0A%0A%0ADefault&=%3C%0A,%0A%0A%0ALayer%202&=%3E%0A.%0A%0A%0ALayer%203&=%3F%0A%2F%2F%0A%0A%0ALayer%204&_w:2.75%3B&=%0AShift%3B&@_c=%23c7c3b5&t=%23ba1312&w:1.25%3B&=%0AFN&_w:1.25%3B&=%0AOption&_w:1.25%3B&=%0ACMD&_c=%233c4041&t=%23aba18b&p=DCS%20SPACE&w:6.25%3B&=&_c=%23c7c3b5&t=%23ba1312&p=DCS&w:1.25%3B&=%0ACMD&_w:1.25%3B&=%0AOption&_c=%233c4041&t=%23aba18b&w:1.25%3B&=%0APn&_w:1.25%3B&=%0ACtrl)
