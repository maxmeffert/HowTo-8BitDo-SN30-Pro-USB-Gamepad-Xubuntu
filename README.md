# How to use 8BitDo SN30 Pro USB Gamepad with Xubuntu

This Guide shows how to use the _8BitDo SN30 Pro USB Gamepad_ with Xubuntu.

The _8BitDo SN30 Pro USB Gamepad_ has two _Controller Modes_
1. Switch Mode
2. X-input

The latter (X-input) let's us pair the gamepad as XBox controller, which is one of the simpler ways to pair your gamepad with Xubuntu.

## Install XBox Controller Driver
First we install the XBox controller driver:

```
sudo apt-get install xboxdrv
```

## Disable Other Drivers
Because we cannot have multiple drivers running for the same device we need to disable `xpad`:

```
sudo rmmod xpad
```

We may need to run that command again after restart before each connect.

## Connect 8BitDo SN30 Pro USB Gamepad
To connect we simply run:

```
sudo xboxdrv
```

This will print the connection information and all events to the terminal like:
```
xboxdrv 0.8.8 - http://pingus.seul.org/~grumbel/xboxdrv/ 
Copyright © 2008-2011 Ingo Ruhnke <grumbel@gmail.com> 
Licensed under GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html> 
This program comes with ABSOLUTELY NO WARRANTY. 
This is free software, and you are welcome to redistribute it under certain conditions; see the file COPYING for details. 

Controller:        Microsoft X-Box 360 pad
Vendor/Product:    045e:028e
USB Path:          003:003
Controller Type:   Xbox360

Your Xbox/Xbox360 controller should now be available as:
  /dev/input/js0
  /dev/input/event16

Press Ctrl-C to quit, use '--silent' to suppress the event output
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:     0 Y1:     0  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
...
```

Here the _8BitDo SN30 Pro USB Gamepad_ is connected as: `/dev/input/js0`

Now we can check if all buttons are working.
Pressing any button will change the zeros to ones (or other numbers for X1,X2,Y1 and Y2).

For actual use we just use
```
sudo xboxdrv --silent
```

That's it!


## References
1. https://www.8bitdo.com/sn30-pro-usb-gamepad/
2. https://www.howtoforge.com/tutorial/how-to-configure-your-gamepad-on-ubuntu/
3. https://askubuntu.com/questions/1082857/8bitdo-sn30-pro-does-it-work-with-linux
