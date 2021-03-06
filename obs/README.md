# Demo2Obs
Automatically export .dem files to video files using OBS.

## Requirements
* Python 3.6+
* OBS Studio
#### Optional
* pidof(1) - Required for GNU/Linux auto restart on crash

## Features
* Record demos with OBS
* Demos are recorded with a descriptive file name
* Automatically goes to the next demo
* 1:1 recording time
* Customizable time padding for both killstreaks and bookmarks
* Groups close clips together
* (GNU/Linux ONLY) Optionally auto-restart TF2 on crash
* Cross platform (GNU/Linux, Windows, and Mac)

## Reason for Existing
### TF2 Demo Export is very slow
I've found that exporting demos, especially for high frame rates and resolutions, can have over a **1:75 demo-time to recording time**. Because this uses real-time recording, **Demo2Obs is 1:1**.
### TF2 Demos don't behave the same when recorded
Many things are erroneously tied to real-time instead of demo-time, such as the bobbing of 3d player models and other HUD effects. Demo2Obs does not have this issue.

## Drawbacks
### "Lossy recording"
TF2's built-in exporter will record everything at the exact frame rate and parameters you set, regardless of resources (albeit very, very slow). Demo2Obs doesn't care about this and will record exactly what it sees. If your recording has a big lag spike, it will be seen on the exported video.
### Audio poisoning
OBS will pick up anything that you set in your audio input settings, including noise from other applications. You can mess with your settings to get around this.

## Setup
**Video coming soon**
1. Download/clone this repository.
2. Open OBS Studio
    1. In the top left, click Tools -> Scripts.
    2. In the bottom left, click the + button.
    3. Navigate to where you downloaded this repository and open *obs.py*.
    4. You should now see the script as loaded.
    5. Copy & paste the path to your recording folder (under *Output* in Settings).
    6. Make a new folder called "results" in "...Team Fortress 2/tf/" and copy & paste the path into Watch Folder.
3. Use Events to VDM to generate VDM files.
4. Open TF2 and configure OBS to record it
5. Go back to the OBS scripts page  and hit "Start" (note, it is recommended you check Script Log to make sure you don't have errors!).
6. Run `playdemo demofile`, replacing demofile with the first demo in the folder provided.
