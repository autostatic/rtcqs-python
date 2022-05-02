# rtcqs

## Introduction

rtcqs is a Python utility to analyze your system and detect possible bottlenecks that could have a negative impact on the performance of your system when working with Linux audio. It is heavily inspired by raboof's excellent [realtimeconfigquickscan](https://github.com/raboof/realtimeconfigquickscan) script in Python.

## Features

Basically the same as realtimeconfigquickscan:
- Root check
- Audio group check
- Background process check
- CPU frequency check
- High resolution timers check
- System timer check
- Preempt RT check
- rtprio check
- Swappiness check
- max_user_watches check
- Filesystem check

Additional features:
- Spectre/Meltdown mitigations check
- Basic IRQ check of sound cards and USB ports
- Power management check
- Qt GUI
- tkinter GUI

## Usage

When writing this script I could rely on Python's built-in functionality so no extra modules are needed, just Python 3. To run the script first clone this repository.

```
git clone https://codeberg.org/rtcqs/rtcqs.git
```

Then cd into the newly created directory.

```
cd rtcqs
```

And run the script.

```
./rtcqs.py
```

## GUI

rtcqs comes with two GUI's, a basic and light tkinter GUI and a polished and heavy Qt GUI. To run the GUI first install the PySimpleGUI (tkinter) or PySimpleGUIQt (Qt) module either in your home directory or in a virtual environment. Bear in mind that the Qt version will pull in a lot of dependencies.

### Home directory

Make sure `pip` is installed, on Ubuntu this would be the `python3-pip` package. For the tkinter GUI you will also need `python3-tk`. Then install PySimpleGUI or PySimpleGUIQt for your user.

For the tkinter GUI you will need the PySimpleGUI module.
```
pip install PySimpleGUI
```

For the Qt GUI you will need the PySimpleGUIQt module.
```
pip install PySimpleGUIQt
```

### Virtual Environment

Make sure the virtual environment module is installed, on Ubuntu this would be `python3-venv`. Then create a virtual environment in the rtcqs directory and install PySimpleGUI or PySimpleGUIQt in there.

For the tkinter GUI use the following commands.
```
python3 -m venv venv &&
. venv/bin/activate &&
pip install --upgrade pip setuptools PySimpleGUI
```

For the Qt GUI use the following commands.
```
python3 -m venv venv &&
. venv/bin/activate &&
pip install --upgrade pip setuptools PySimpleGUIQt
```

You can now run the GUI with either `./rtcqs_simple_gui.py` for the tkinter GUI or `./rtcqs_gui.py` for the Qt GUI. Next time you'd like to run the GUI load the virtual environment again and spin up the GUI.

For the tkinter GUI:
```
. venv/bin/activate
./rtcqs_simple_gui.py
```

For the Qt GUI:
```
. venv/bin/activate
./rtcqs_gui.py
```

### Overview

When running the GUI it will immediately show the results of the checks. All checks have their own tab. Each tab title consists of a symbol that shows the check result and the name of the check. A ✔ means the check was successful while a ✘ means rtcqs encountered an issue. This way you can quickly spot which checks have issues.

Clicking 'Cancel' will close rtcqs. Clicking 'About' will bring up a popup window which displays the version and a short description.

<p align="center">
<img src="https://codeberg.org/attachments/5345ce8a-773a-448a-9bac-a2fe5fd44b94">
<br>
<em>rtcqs main window (Qt version)</em>
<br>
<br>
<img src="https://codeberg.org/attachments/4dc26f40-76c9-4738-bfff-c57457f7f9bb">
<br>
<em>rtcqs about window (Qt version)</em>
</p>

<p align="center">
<img src="https://codeberg.org/attachments/dd6de9ba-670d-4aa1-9b3c-b7de876899db">
<br>
<em>rtcqs main window (tkinter version)</em>
<br>
<br>
<img src="https://codeberg.org/attachments/9d0fe041-1209-4227-a603-dfed4ef10ba1">
<br>
<em>rtcqs about window (tkinter version)</em>
</p>

## Future plans

- Make the project more dynamic and modular so it gets easier to add new features

## Contact

To contact me send me a mail or if it's a technical issue or question, use this project's issue tracker.

## Thanks

Many thanks of course to the original author of realtimeconfigquickscan, Arnout Engelen a.k.a. raboof.