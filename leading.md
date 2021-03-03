# Leading

- [Introduction](#leading-introduction)
- [Click Leading](#click-leading)
- [Connection Leading](#connection-leading)
- [Backtrack](#backtrack)
- [Playhead](#playhead)
    - [Follow Along](#follow-along)
    - [Playhead Selection](#playhead-selection)

---
<a name="leading-introduction"></a>
## Introduction

Leading is the process of positioning the timeline to a specific point in time. This functionality can either be driven by you as you click on a stamp in the timeline or by a <a href="/docs/connections"><b>connection</b></a>. When the timeline is lead to a point in time the targeted flag stamp and its attached media will seek to that moment allowing you to quickly traverse and analyse the timeline. 

---
<a name="click-leading"></a>
## Click Leading
When a stamp is clicked on and it sits with the range of the targeted flag stamps attached media, click leading will seek the media to the point in time the stamp sits. Click leading is designed as a toggle state to allow for situations where edits/selection can be made on a stamp without altering the current playback of a piece of media. To turn click leading on or off, use the keyboard shortcut `Ctrl` `Shift` `⌘` `L` or press the button in the toolbar.

---
<a name="connection-leading"></a>
## Connection Leading
Typically <a href="/docs/connections"><b>connections</b></a> are used to listen for and log events on the timeline by creating a stamp when a certain message is received. Instead of creating a stamp it is useful for a connection to lead the media by looking for an already created stamp with identical attributes and leading to that. The most likely case where you would want to do this is after a recording has been made and you would like the connection to drive the media playback e.g. In a notes sessions where a connection to a lighting console has been used to log cues being fired alongside a video recording, you would now like to "Go To Cue" from the console and the media in Stamp to be lead to the correct position.

```note
Note: Connection leading looks for stamps within the range of the current targeted flag stamps media with identical attributes. e.g. An eos connection receiving a cue list 1, cue 2 fired message would look for an eos stamp with cue list 1 and cue 2 as its attributes and lead to the first one it found.
```

---
<a name="backtrack"></a>
## Backtrack
Backtrack is a way to preroll the media so that you can watch as it runs into a Stamp and works in conjunction with click leading. When a Stamp is clicked in preview mode, instead of leading to the moment the Stamp sits on the timeline it will lead to a specified amount before. The amount of backtrack can be set in `Preferences` -> `Time`. To turn backtrack on or off, use the keyboard shortcut `Ctrl` `Shift` `⌘` `B` or press the button in the toolbar.

---
<a name="playhead"></a>
## Playhead
Whilst in preview mode a playhead is shown on the timeline indicating the position of the targeted flag stamps attached media.
Whilst the media is running, lead to or positioned by the scrub bar the playhead will update, typically moving down the timeline.

<a name="follow-along"></a>
### Follow Along
Follow along is designed as a convenience to automatically scroll the timeline to show the playhead. To turn follow along on or off, use the keyboard shortcut `Ctrl` `Shift` `⌘` `F` or press the button in the toolbar.

<a name="playhead-selection"></a>
### Playhead Selection
Playhead selection emphasises the playhead position by selecting the stamp the playhead sits on. To turn playhead selection on or off, use the keyboard shortcut`Ctrl` `Shift` `⌘` `P` or press the button in the toolbar.
