---
layout:     post
title:      "Building cen64 on macOS"
date:       2020-01-11 17:42:41 +0000
categories: n64
---
For testing Nintendo 64 homebrew ROMs, [cen64](https://github.com/n64dev/cen64) is the most accurate emulator (though it doesn't run at full speed yet). Here's how to build it from source on macOS:

1. Install XQuartz from the official [distributed disk image](https://www.xquartz.org/)
1. `git clone https://github.com/n64dev/cen64.git`
1. `cd cen64`
1. `mkdir build`
1. `cd build`
1. `cmake ..`
1. `make`

If you'd like to enable cen64's debug logging, create a debug build when running `cmake`:

    cmake -DCMAKE_BUILD_TYPE=Debug ..

When running cen64 outside of an XQuartz X11 terminal, it may report:

    Using NTSC-U PIFROM
    create_device: Failed to initialize the VI.
    Failed to create a device.

To fix this, you can run it within an XQuartz X11 terminal, or simply set the `DISPLAY` environment variable to something like `:0` either in your `.bashrc` file or inline during invocation:

    DISPLAY=:0 ./cen64 /path/to/pifdata.bin /path/to/rom.z64

`DISPLAY` needs to be set because cen64 calls [XOpenDisplay](https://tronche.com/gui/x/xlib/display/opening.html) with a NULL display name (presumably to default to your `DISPLAY` environment variable), but if it's not set, XOpenDisplay returns NULL and cen64 has no display within which to create a window for rendering Nintendo 64 content.

For extremely verbose register-level output, edit `CMakeLists.txt` and set `DEBUG_MMIO_REGISTER_ACCESS` to `ON`. Make sure to remove any cached data in `build/` to ensure your changes are reflected, then recompile and re-run.
