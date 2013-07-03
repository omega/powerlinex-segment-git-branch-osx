# Powerline eXtenstion for git branch that works on OS X

For some reason the main powerline git branch segment decided to stop working
on OS X. Well, technically it still worked, it just spit out an annoying and
misleading error message every time powerline was displayed about "libc is too
old". What the error message really meant was "This feature tries to use
inotify, but the developer was too lazy to provide propper fall backs for
anything but inotify on linux, and too lazy to provide a proper error message
for anybody else"

This segment tries to mimic the old behaviour, of just working.

First install the addon:

    pip install -U --user git+https://github.com/omega/powerlinex-segment-git-branch-osx.git

The name will re-use the theme config from the main branch segment. If you make
a theme, you can include a custom `segment_data`:

    "branch": {
        "before": " "
    },

And then add this to your prefered spot under `segments`:

    {
        "module": "powerlinex.segment.git-branch-osx",
        "name": "branch",
        "args": {
            "status_colors": true
        }
    },

To have this replace your old segment, just add the `module` line to your shell
theme, and everything will work on your mac again :)
