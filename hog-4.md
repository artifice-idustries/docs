# Hog 4 Connection

- [Introduction](#hog-introduction)
- [Which Connection Protocol?](#tcp-or-udp)
- [TCP](#hog-tcp)
    - [OSC Versions](#tcp-osc-versions)
    - [Hog 4 Settings](#tcp-hog-settings)
    - [Stamp Settings](#tcp-stamp-settings)
- [UDP](#hog-udp)
    - [Hog 4 Settings](#udp-hog-settings)
    - [Stamp Settings](#udp-stamp-settings)
- [Cue Lists](#hog-cue-lists)
    
---
<a name="eos-introduction"></a>
## Introduction

The hog 4 family connection logs playback actions by a Hog 4 family console creating <a href="/docs/type"><b>hog stamps</b></a> whenever an OSC address pattern prefixed with `/hog/playback/` is received. A hog 4 connection utilises the OSC API provided by High End Systems and requires to a varying degree setup at the console for messages to be successfully sent to Stamp. Whilst working with a hog 4 family connection we recommend you also refer to HES's <a href="https://www.highend.com/products/consoles"><b>Hog 4 OS User Manual</b></a>, specifically the Open Sound Control (OSC) section.

When a hog 4 family connection receives a playback message from a hog 4 family console it will create a <a href="/docs/type"><b>hog stamp</b></a> assigning the `cue list`, `cue number`, `scene` or `macro` values accordingly.

---
<a name="tcp-or-udp"></a>
## Which Connection Protocol?
Before getting started, be sure to understand which connection protocol (TCP or UDP) you aim to use.

TL;DR: TCP is slower but reliable, UDP is faster but unreliable. Realistically in a small, closed and stable network typical for a live production, speed is negligible so **we would recommend using TCP** for the key points that it is both quicker and easier to set up. Feel free to read this <a href="https://blog.etcconnect.com/2018/01/exploring-the-network-the-postman/"><b>blog post</b></a> written by our founder for a more in depth look at the differences.

---
<a name="hog-tcp"></a>
## TCP

<a name="tcp-osc-versions"></a>
### OSC Versions

When using OSC via TCP it is important to distinguish that there are two versions of the OSC protocol in circulation. TCP is a stream of data and so there is a requirement when parsing OSC data to understand the end of one packet or "message" and the beginning of the next. This is done by packet framing. In OSC 1.0 a packet length header is used to determine the length of each packet where as in 1.1 the more robust double END SLIP <a href="https://tools.ietf.org/rfc/rfc1055.txt"><b>(RFC 1055)</b></a> protocol is used that uses a special character to identify the end of a packet.

Ultimately both stamp and hog 4 consoles can work with both versions but a distinction needs to be made by you as to which version you want to use and should be set accordingly in both the settings of the hog 4 console and the hog 4 connection within stamp.

<a name="tcp-hog-settings"></a>
### Hog 4 Settings
1. From the Network Window navigate your way through Settings to the Open Sound Control pane and enable both OSC In and OSC Out.

2. Set the Output IP address to the IP address of the mac running Stamp with a port number of your choice e.g 7001.

3. Set the Protocol to the TCP framing of your desired OSC version.

<a name="tcp-stamp-settings"></a>
### Stamp Settings
1. Input the IP address of the hog 4 console.

2. Input the port number you set on your hog 4 console as the port for the connection.

3. Select the same OSC version as the one being used by the hog 4 console. 

4. Check `Connect via TCP`

5. Click `Save`

---
<a name="hog-udp"></a>
## UDP

<a name="udp-hog-settings"></a>
### Hog 4 Settings

1. From the Network Window navigate your way through Settings to the Open Sound Control pane and enable both OSC In and OSC Out.

3. A transmit and receive port number should be chosen e.g. 7001 and 7002, then input into the input port and output port fields respectively.

4. Input the IP address for the mac running Stamp into the output IP address field.

3. Set the Protocol to UDP.

<a name="udp-stamp-settings"></a>
### Stamp Settings

1. Input the IP address of the hog 4 console.

2. Uncheck `Connect via TCP`

3. Input the input port you set on your hog 4 console as the transmit port for the connection.

4. Input the output port you set on your hog 4 console as the receive port for the connection. 

4. Click `Save`

```note
Note: Make sure to swap the transmit/output and receive/input port numbers between the hog 4 console and the connection in Stamp. It is a common mistake to have the port numbers for both transmit and receive as the same.
```

---
<a name="hog-cue-lists"></a>
## Cue Lists
A hog 4 family connection can either listen and log cues fired from all cue lists or a selection. The input for multiple lists should be separated by a comma.
For example, to listen and log cues that are from cue lists 1, 2 and 999:
```stamp
1,2,999
```
