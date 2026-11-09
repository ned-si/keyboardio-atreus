# keyboardio-atreus

My QMK keymap for the [Keyboardio Atreus](https://shop.keyboard.io/products/keyboardio-atreus).

It is cloned inside my
[qmk-userspace](https://github.com/ned-si/qmk-userspace) checkout, at
`keyboards/keyboardio/atreus/keymaps/nedsi` (git-ignored there, so the userspace always
builds whatever this clone has checked out).

It uses the shared code in `users/nedsi`: layer enum, row macros, custom keycodes,
tap dances. The gaming row macros and the gaming toggle on the NAV layer are
defined in `keymap.c`, since the shared code no longer has them.

## Build and flash

From a machine set up as described in the qmk-userspace README:

```sh
qmk compile -kb keyboardio/atreus -km nedsi
qmk flash   -kb keyboardio/atreus -km nedsi
```

Bootloader: press the reset button on the underside, hold the top-left key
while plugging in, or `QK_BOOT` (the Q position on the MISC layer, or the
bottom-left key on the NAV layer). The Atreus uses the Caterina bootloader,
which only waits about 8 seconds: start `qmk flash` first.
