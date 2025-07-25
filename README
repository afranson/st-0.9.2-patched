# A patched st with version 0.9.2

Incorporates the following patches
- alpha
- anysize
- drag n drop
- ligatures
- undercurl
- scrollback
- scrollback-reflow
- scrollback-mouse
- scrollback-mouse-altscreen

## Reason for existence

The difficult patch for this generation is alpha. Until it is updated, patchers need to know that even after correctly patching, they may need to implement the following change to "x.c" in the ```xinit``` function.

After patching, these lines will be in x.c:
```c
	dc.gc = XCreateGC(xw.dpy, xw.win, GCGraphicsExposures,
			&gcvalues);
	xw.buf = XCreatePixmap(xw.dpy, xw.win, win.w, win.h,
			xw.depth);
```

They actually need to be reversed and xw.win needs to be xw.buf as seen below:
```c
	xw.buf = XCreatePixmap(xw.dpy, xw.win, win.w, win.h,
			xw.depth);
	dc.gc = XCreateGC(xw.dpy, xw.buf, GCGraphicsExposures,
			&gcvalues);
```

All the other patches are pretty straightforward to use. Some fail to work automatically with the 'patch' tool, but they are simple to resolve.
