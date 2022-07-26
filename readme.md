# What?
Run any X application under a minimal Window Manager, `jwm`.


# Why?
Convenience. And separation of concerns.
Lets people resize/maximize windows, when run under `expose-as-vnc-server`.

(Also, Saleae Logic GUI 2 needs a proper headless mode)


# How?
We already have a $DISPLAY, but it has no window manager.
So we start `jwm` in the background but give it an empty config file ~ "kiosk" mode.

Payload X application is run, blockingly.

When the payload command exits, `jwm` is killed and script exits.

Payload command's exit code is propagated all the way.


# "Installation"
* Install dependencies: `jwm` (Joe's Window Manager).
* Git clone this repo to somewhere locally
* Add to PATH: `export PATH=$PATH:<where you cloned to locally>`


# Usage Example

Start `xterm` as payload, running as the sole application under `jwm`:
```
$ jwm-run xterm
```
