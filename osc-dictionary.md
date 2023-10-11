# Stamp OSC Dictionary

An API (application program interface) for OSC enabling you to control Stamp from any device or software that can send OSC packets.

## Transport Layer

The Stamp OSC API can be used by either UDP and TCP transport layers. Stamp listens for incoming OSC packets on port 24601. When talking to Stamp via TCP, packets are framed using the double END SLIP protocol [RFC 1055](https://tools.ietf.org/rfc/rfc1055.txt) as required by the [OSC 1.1 specification](http://opensoundcontrol.org/introduction-osc).

## Reply Format

All replies from Stamp take the form:

`/stamp/reply/{invoked/osc/message} {arguments}`

## OSC Methods

Methods will be sent to the current, front-most, active timeline document. So, if `romeo and juliet.stamps` timeline is the front-most, active document, and you send Stamp the OSC command /stamp/media/recorder/start, then `romeo and juliet.stamps` will start recording.

### Timeline Methods

**/stamp/timeline/note {note} {colour}**

if `note` is given, create a note stamp and set the note to the specified note. If not, create an empty note stamp.

if `colour` is the given, the new note stamp will be created with the colour. Supported strings include: `green`, `red`, `yellow` or `purple`. Colour will default to `green`.

### Media Methods

#### Recorder

**/stamp/media/recorder**

Read-only: return `true` if media is currently recording, otherwise `false`.

**/stamp/media/recorder {bool}**

If `bool` is true, start recording media. 
If `bool` is false, stop recording media.

**/stamp/media/recorder {number}**

`number` is interpreted as a boolean; 0 equals `false`, any other number equals `true`.

**/stamp/media/recorder/start**

Start recording media.

**/stamp/media/recorder/stop**

Stop recording media.

#### Playback

**/stamp/media/playback**

Read-only: return `true` if media is currently playing, otherwise `false`.

**/stamp/media/playback {bool}**

If `bool` is true, start media playback. 
If `bool` is false, pause media playback.

**/stamp/media/playback {number}**

`number` is interpreted as a boolean; 0 equals `false`, any other number equals `true`.

**/stamp/media/playback/start**

Start media playback.

**/stamp/media/playback/pause**

Pause media playback.

### Miscellaneous Methods

**/stamp/remind**

A simple heartbeat method. Returns a `string` that may help you to remember. "Who am I? 24601!".
