# picom-manager
Custom script to manage Picom behavior on Cereus Linux.
This tool was developed with the main purpose to provide multiple backend configurations depending of machine hardware. 

        Usage: picom-manager [OPTION]...

        OPTIONS:
        -c [CONFIG_FILE]         Custom configuration path to use.
        -d                       Override picom-manager configurations and use user-defined instead.
        -h                       Shows this help.
        -f [--flag]              Add an extra flag to compositor. May be used many times.
        -m [MODE]                Override environment compositor mode. Possible values are: off, compatibility, opengl and blur.
        -t                       Toggle the compositor."

Cereus by default will use GLX backend, but if this script detects an error at Picom startup, it will inmediately fallback to XRender.

## Environment variables

<code>picom-manager</code> works with environment variables. The most important is <code>$COMPOSITOR_MODE</code>. In LXQt ISOs this is defined at <code>~/.config/lxqt/session.conf</code>, but if you want to define it to <code>~/.profile</code> you MUST remove it from LXQt configuration first (this isn't necessary for any other desktop environment). 

Supported compositor modes are: <code>off</code> (disable compositor), <code>compatibility</code> (XRender backend), <code>opengl</code> (GLX backend) and <code>blur</code> (blur effects with GLX backend).

### Why not just use .profile for every desktop?

LXQt allows to define environment variables graphically. We consider this ideal for begginner users.

## Using on other distributions

You could probably use this tool in other distros, it does needs to be patched first to not use certain Cereus specific paths and commands. We'll consider doing this in the future.
