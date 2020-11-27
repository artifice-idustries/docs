# Command Palette

- [Introduction](#command-palette-introduction)
- [Timestamp](#timestamp)
    - [Pre Typing](#pre-typing)
    - [Post Typing](#post-typing)
    - [Media Timestamp](#media-timestamp)
- [Media Control](#media-control)
	- [Pause](#pause)
	- [Resume](#resume)
- [Commands](#commands)
    - [Colour](#colour)
    - [Type](#type)

---
<a name="command-palette-introduction"></a>
## Introduction

The Command Palette provides access to many commands and enables you to create stamps of varying types providing them with different attribute values from a single command.
To quickly bring focus to the Command Palette, use the keyboard shortcut `Shift` `⌘` `P`.

---
<a name="timestamp"></a>
## Timestamp
The timestamp for a stamp can be taken from one of two points within the process of creating a stamp from the command palette. Before (pre) or after (post) you have typed text.
```default
Default Value: Post Typing
```

<a name="pre-typing"></a>
### Pre Typing
With an empty command palette press `↵`. Stamp will remember the timestamp and apply it to the created stamp once text has been typed and a second `↵` has beed pressed. 


Further presses of the `↵` key, with an empty command palette, will update the remembered timestamp. 
```note
Note: The placeholder text in the command palette changes as you update the timestamp.
```
The command palette's timestamp can be reset from the `Entries` menu by clicking `Reset Time` or by using the keyboard shortcut `Ctrl` `R`. This will put the command palette back to applying timestamps in a post typing fashion.

<a name="post-typing"></a>
### Post Typing

By default the timestamp applied to a stamp, created from the command palette, will be taken from the point at which you press enter after typing out text.

<a name="media-timestamp"></a>
### Media Timestamp
When enabled media timestamp forces Stamp to create editable stamps with a timestamp that corresponds to the medias playback position. The functionality ignores real-time and calculates the timestamp needed to position the created stamp at the exact spot where the medias playback position lies.

The feature only takes effect when in `Preview` mode and can be toggled on or off with the keyboard shortcut `Shift` `⌘` `T`.
```default
Default Value: Enabled
```
---
<a name="media-control"></a>
## Media Control

<a name="pause"></a>
### Pause

When in `Preview` mode with media currently playing, it is possible for Stamp to automatically pause the media as you begin typing. This functionality is helpful when you are making notes or positioning cues against a piece of media as the pause allows you time to write text before moving on. Remember you will want `Media Timestamp` turned on in this situation.

To enable this functionality tick `Pause Media when editing` in `Preferences`.
```default
Default Value: Disabled
```
<a name="resume"></a>
### Resume

When in `Preview` mode with media currently paused, it is possible for Stamp to automatically play the media once text has been typed, `↵` has been pressed and a stamp has been created. This functionality is particularly helpful in conjunction with the `Pause` feature, when you are making notes or positioning cues against a piece of media, encouraging momentum and a faster workflow.

To enable this functionality tick `Resume Media on creation of new Stamp` in `Preferences`.
```default
Default Value: Disabled
```
---
<a name="commands"></a>
## Commands

<a name="colour"></a>
### Colour

The command palette can be changed to create editable stamps with different colours either from the `Entries` menu by clicking the desired colour in the `Colour` section or by typing the following commands into the command palette:

[/green](#colour-green)
[/red](#colour-red)
[yellow](#colour-yellow)
[/purple](#colour-purple)

The default colour the command palette is set to when opening a timeline can be changed in `Preferences`.
```default
Default Value: Green
```
<a name="type"></a>
### Type

The command palette can be changed to create the different types of editable stamps either from the `Entries` menu by clicking the type in the `Stamp Type` section, using their <a href="/docs/keyboard-shortcuts"><b>Keyboard Shortcut</b></a> or by typing the following commands into the command palette:

[/session](#session-type)
[/flag](#flag-type)
[/note](#note-type)
[/cue](#cue-type)

```default
Default Value: Note
```
