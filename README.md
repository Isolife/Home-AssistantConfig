# Home Assistant Config - Isolife

This is my [Home Assistant](https://home-assistant.io/) configuration.

## Overview

* [Git Push](#git_push)
* [Latest build](https://travis-ci.org/Isolife/Home-AssistantConfig)

## Some of the devices and services that I use with Home Assistant
* [Philips Hue](https://www.philips.no/c-m-li/hue)
  - With [Sleep as Android](https://sleep.urbandroid.org/) my bedroom lights turn on as the alarm starts.


* [Bose Soundtouch](https://www.bose.co.uk/en_gb/products/speakers/multi_room_speakers.html)
  - Starts playing music in the morning (Confirurable with the input_datetime component)

* Media
  - [Plex](https://www.plex.tv/) for media consumption along with [Plex component](https://home-assistant.io/components/media_player.plex/)

<a name="git_push"></a>
## Git Push

Activate the virtual environment

`cd /home/pi/.homeassistant/ && source /home/pi/homeassistant/bin/activate`

Check if configuration is working:

`hass --script check_config`

ok?

`git status`

Look at the files that have changed, and look at the files that aren’t under version control yet (“untracked”). Don’t blindly add everything with “git add .”, that will just cruft up your repo over time. Are there new files you want to version control? Then add them with git add . But you don’t need to version control old logs or other cruft. Keep your repo clean with only what you would need if you had to start fresh.

Then, for each file that has changed, do:

`git diff <filename>`

and look at what has actually changed. Make sure it’s a change you want to keep. Only then commit it with:

`git commit -m "describe changes" <filename>`

If you have a change that’s logically coherent but spans several files, e.g., you added a new device and got it customized and into your groups, try to group those into one commit.

If you spot things that were intended to be temporary and want to “undo” the changes in that file, or you got yourself into a problem that you want to back out of, go back to your last committed version with

`git checkout <filename>`

Repeat until git status is clean. Then push your repo back to github:

`git push origin master`
