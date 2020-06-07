# telegram.py
[![Build Status](https://travis-ci.org/yshalsager/telegram.py.svg?branch=master)](https://travis-ci.org/yshalsager/telegram.py)

[![GitHub release](https://img.shields.io/github/release/yshalsager/telegram.py.svg)](https://github.com/yshalsager/telegram.py/releases/)
[![Download](https://img.shields.io/github/downloads/yshalsager/telegram.py/total.svg)](https://github.com/yshalsager/telegram.py/releases/latest)

[![Open Source](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)

A slim script, written in python, allows you to send messages via your telegram bot.

Inspired from [telegram.sh](https://github.com/fabianonline/telegram.sh/)

## Bot configuration

* Create a bot at telegram:
  * Search for the user `@botfather` at telegram and start a chat with him.
  * Use the `/newbot` command to create a new bot. BotFather will give you a
    token. Keep this.
* Use your telegram client to send a message to your new bot. Any message
    will do.

## Using the script

* Get the latest copy of `telegram.py` and run it with:
  * The required arguments: `(-c CHAT)` and one of the following options `(-M MESSAGE | -P PHOTO | -V VIDEO | -A AUDIO | -F FILE)`
  * Optional arguments: `(-p yes/no)` to disable/enable URL preview. `(-c TEXT)` to add a caption with Media/Documents. `(-s yes/no)` to disable/enable message notification sound.
* The default parse mode is `Markdown`. If you want to use HTML use the flag `(-m HTML)`
* It will use the bot api from your environment variable as BOT_API else it will not work.
`export BOT_API="xxxxx:xxxxx"`

## Some examples of usage:

- Sending normal text:

`python telegram.py -c @TestChannel -M "Hello"`

- Sending markdown text:

`python telegram.py -c @TestChannel -M "*Hello*"`

- Sending HTML text:

`python telegram.py -c @TestChannel -M "<b>Hello</b>" -m HTML`

- Sending link with preview:

`python telegram.py -c @TestChannel -M "this is a [link](https://github.com/yshalsager/telegram.py)" -p no`

- Sending link without preview:

`python telegram.py -c @TestChannel -M "This is a [link](https://github.com/yshalsager/telegram.py)"`

- Sending photo:

`python telegram.py -c @TestChannel -P avatar.png`

- Sending photo with caption:

`python telegram.py -c @TestChannel -P avatar.png -C "Logo"`

- Sending photo with HTML caption:

`python telegram.py -c @TestChannel -m HTML -P avatar.png -C "<b>Logo</b>"`

- Sending GIF:

`python telegram.py -c @TestChannel -G small.gif`

- Sending video:

`python telegram.py -c @TestChannel -V video.mp4`

- Sending video note:

`python telegram.py -c @TestChannel -N video.mp4`

- Sending audio:

`python telegram.py -c @TestChannel -A audio.mp3`

- Sending voice message:

`python telegram.py -c @TestChannel -O voice.mp3`

- Sending file:

`python telegram.py -c @TestChannel -F file.zip`

- Sending file with HTML caption:

`python telegram.py -c @TestChannel -m HTML -F file.rar -C "<b>File</b>"`

- Sending sticker:

`python telegram.py -c @TestChannel -s <stickerid>`

## Using binary files:

If you want to use binary executable file for Windows and Linux check [releases](https://github.com/yshalsager/telegram.py/releases)! It's compiled with [pyinstaller](https://www.pyinstaller.org/).

Note that builds which automatically generated using travis-ci doesn't have a tag. If you prefer to go for stable release get the latest tagged one.

