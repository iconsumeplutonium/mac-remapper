# Mac Remapper

This remaps the Mac 2008 keyboard's Left Option and Left Command keys, to match LWin and LAlt on Windows.

![Mac Keyboard](images/mac_keyboard.jpg)

(Image source: [Xah Lee](http://xahlee.info/kbd/apple_keyboard_history.html))

Command serves as super/Windows on Windows and option serves as alt, which is flipped. To fix this, you can use `mac_remapper.ahk`.

# WARNING
Do not unplug and replug more than 10 times, the driver cannot detect the device after that

# Known Issues
Ctrl-Alt-Del doesn't work, this is because this is intercepted at the hardware level. For now, use RAlt, I guess.

# Requirements & Installation
First, install [AutoHotKey](https://www.autohotkey.com/). <br> Then, install the [AutoHotInterception Driver](https://github.com/evilC/AutoHotInterception).

Now, you have to check your hardware ID using `Monitor.ahk` (source: AutoHotInterception Repo).

![AHInterception Monitor](images/monitor.jpg)

Pull this repo.

Click on each of the IDs (ONE AT A TIME! Select more than one and it can crash your device) and type on your keyboard until you get signals from the desired keyboard (for me, this was ID7). Note down the VID and PID.

Once you have this, modify `mac_remapper.ahk` and modify this line: <br>
`id1 := AHI.GetKeyboardId(<VID>, <PID>, 1)` <br>
With your VID and PID.

Finally, set `mac_remapper.ahk` to run on startup and you're good to go!

# Special Thanks
- [sameerdash2](https://github.com/sameerdash2) for debugging this README