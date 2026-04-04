---
title: "Python venv Tutorial"
date: 2026-04-04
description: "Setup venv, clone existing repos, understand virtual environments for python"
tags: ["devops", "python", "github", "beginner"]
showTableOfContents: true
---

## What is a venv?

A venv is a virtual environment, used to isolate and replicate exact environment settings.    If you tested code in one environment, it may not work in another without a venv setup the same way as the original.

## pip freeze

`pip freeze`  will list the modules in your current environment space.    It's also used to create the `requirements.txt` that many people use when sharing scripts.    `pip freeze > requirements.txt` will create the requirements.txt file with a list of all of the modules in your current environment.   You can later use it to recreate that environment.


## Sample Install

### Clone A Repo/Git

Typically you would have a repo  with source code, that you'd like to work on/use.    You can use the diagramming software I wrote as a demo (it's similar to draw.io)

```
git clone https://github.com/rubysash/python-diagrams.git
```

After you've downloaded the files, you setup a venv in that same directory.  If you are making your own, new venv for a different project just use a different venv name, like `python -m venv something`.  The example below assumes you tested by cloning the repository above.


### Windows Install
```
python -m venv python-diagrams
cd python-diagrams
scripts\activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Linux Install

```
python3 -m venv python-diagrams
cd python-diagrams
source bin\activate
python3 -m pip install --upgrade pip
python3 -m pip install -r requirements.txt
```

## Shortcuts

It's a pain to manaully type `scripts\activate`   or `source bin\activate` so you can script that and use it to start the venv, load your modules, and start your program.

### Windows Batch

Create a file called `start.bat` in the venv directory.   Add this line to it:

```
start cmd /k "Scripts\activate && python main.py"
```

Now you can double click that file and it will load the script in the right venv

### Linux

Linux uses `.desktop` files in the `/home/someuser/Desktop/` folder.   Create this `9mens.desktop` file in that location and modify the lines below.   Replace `someuser` with your actual user name

```
[Desktop Entry]
Version=1.0
Type=Application
Name=Mark Down Maker
Comment=
Exec=sh -c '/home/someuser/python-diagrams/bin/python3 /home/someuser/python-diagrams/main.py'
Icon=account-edit
Path=/home/someuser/python-diagrams
Terminal=false
StartupNotify=false
```

---

## Lab 


### Goal

- Learn how to clone a repo
- Learn how to setup a venv
- Understand venv and why you use them.

### Steps

- Create a new venv using existing code with a requirements.txt
- Start the venv, update pip, then install the modules in the requirements.txt
- Run the the script by the CLI without the batch/bash file
- From a gui explorer, run the script from the shortcut.

