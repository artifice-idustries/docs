# Stamp OSC Dictionary

An API (application program interface) for OSC enabling you to control Stamp from any device or software that can send OSC packets.

## Transport Layer

The Stamp OSC API can be used by either UDP and TCP transport layers. Stamp listens for incoming OSC packets on port 24601.

When talking to Stamp via UDP, each OSC packet corresponds to one UDP datagram. Replies to OSC via UDP are sent to port 24602.

When talking to Stamp via TCP, packets are framed using the double END SLIP protocol [RFC 1055](https://tools.ietf.org/rfc/rfc1055.txt) as required by the [OSC 1.1 specification](http://opensoundcontrol.org/introduction-osc). Replies to OSC via TCP are sent to port 24601.

## Reply Format

All replies from Stamp take the form:

`/stamp/reply/{invoked/osc/message} {arguments}`

## OSC Methods

Methods will be sent to the current timeline which is the front-most, active document. 
So, if `romeo and juliet.stamps` timeline is the front-most, active document, and you send Stamp the OSC command /stamp/media/record, then `romeo and juliet.stamps` will start recording.

### Timeline Methods

**/stamp/timeline/note {string}**

if `string` is given, create a note stamp and set the note to the specified string. If not, create an empty note stamp.

### Media Methods

**/stamp/media/record {bool}**

If `bool` is true or no argument is provided, the message is treated as if there was a boolean value `true`. In either case start recording media. 
If `bool` is false, stop media recording.

**/stamp/media/record {number}**
`number` is interpreted as a boolean; 0 equals `false`, any other number equals `true`. If no number is given start recording media.

**/stamp/media/record/start**

Start media recording.

**/stamp/media/record/stop**

Stop media recording.

**/stamp/media/isRecording**

Read-only: return `true` if media is currently recording, otherwise `false`.

**/stamp/remind**

A simple heartbeat method. Returns a `string` that may help you to remember. "Who am I? 24601!".
