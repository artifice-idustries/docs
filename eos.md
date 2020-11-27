# Eos Family Connection

- [Introduction](#eos-introduction)
- [Which Connection Protocol?](#tcp-or-udp)
- [TCP](#eos-tcp)
    - [OSC Versions](#tcp-osc-versions)
    - [Eos Settings](#tcp-eos-settings)
    - [Stamp Settings](#tcp-stamp-settings)
- [UDP](#eos-udp)
    - [Eos Settings](#udp-eos-settings)
    - [Stamp Settings](#udp-stamp-settings)
- [Cue Lists](#eos-cue-lists)
- [Cue Stamp Leading](#eos-leading)
    
---
<a name="eos-introduction"></a>
## Introduction

The eos family connection logs cues fired by an eos family console creating <a href="/docs/type"><b>eos stamps</b></a> when the OSC address pattern `/eos/out/event/cue/*/*/fire` is received. An eos family connection utilises the OSC API provided by ETC and requires to a varying degree setup at the console for messages to be successfully sent to Stamp. Whilst working with an eos family connection we recommend you also refer to ETC's <a href="https://www.etcconnect.com/Products/Consoles/Eos-Family/"><b>Eos Family Software Operations Manual</b></a>, specifically the Open Sound Control (OSC) section.

When an eos family connection receives the cue fired message from an eos family console it will create an <a href="/docs/type"><b>eos stamp</b></a> assigning the `cue list`, `cue number` and `label` values accordingly.

---
<a name="tcp-or-udp"></a>
## Which Connection Protocol?
Before getting started, be sure to understand which connection protocol (TCP or UDP) you aim to use.

TL;DR: TCP is slower but reliable, UDP is faster but unreliable. Realistically in a small, closed and stable network typical for a live production, speed is negligible so **we would recommend using TCP** for the key points that it is both quicker and easier to set up. Feel free to read this <a href="https://blog.etcconnect.com/2018/01/exploring-the-network-the-postman/"><b>blog post</b></a> written by our founder for a more in depth look at the differences.

---
<a name="eos-tcp"></a>
## TCP

```note
Note: It is possible to connect to a backup or client eos console via TCP but OSC messages are only sent from a console acting as the "Master" console.
```

<a name="tcp-osc-versions"></a>
### OSC Versions

When using OSC via TCP it is important to distinguish that there are two versions of the OSC protocol in circulation. TCP is a stream of data and so there is a requirement when parsing OSC data to understand the end of one packet or "message" and the beginning of the next. This is done by packet framing. In OSC 1.0 a packet length header is used to determine the length of each packet where as in 1.1 the more robust double END SLIP <a href="https://tools.ietf.org/rfc/rfc1055.txt"><b>(RFC 1055)</b></a> protocol is used that uses a special character to identify the end of a packet.

Ultimately both stamp and eos family consoles can work with both versions but a distinction needs to be made by you as to which version you want to use and should be set accordingly in both the settings of the primary eos console and the eos connection within stamp.

<a name="tcp-eos-settings"></a>
### Eos Settings
1. From the Eos Configuration Utility (ECU) navigate your way through Settings to the Interface Protocol Network Settings. The options available to you differ between eos software version but essentially OSC should be enabled for the interface that Stamp will be connected to and the TCP format should be set according to your desired OSC version.

2. From the Show Control Settings within the eos application OSC should be enabled for both receiving and transmitting messages.

```note
Note: Stamp uses port 3032 for the TCP connection.
```

<a name="tcp-stamp-settings"></a>
### Stamp Settings
1. Input the IP address of the primary eos console acting as the "Master". 

2. Select the same OSC version as the one being used by the eos console. 

3. Check `Connect via TCP`

4. Click `Save`

---
<a name="eos-udp"></a>
## UDP

<a name="udp-eos-settings"></a>
### Eos Settings

1. From the Eos Configuration Utility (ECU) navigate your way through Settings to the Interface Protocol Network Settings. The options available to you differ between eos software version but essentially UDP OSC should be enabled for the interface that Stamp will be connected to. 

2. From the Show Control Settings within the eos application OSC should be enabled for both receiving and transmitting messages.

3. A transmit and receive port number should be chosen e.g. 3001 and 3002, then input into the `OSC UDP RX Port` and `OSC UDP TX Port` fields.

4. Input the IP address for the mac running Stamp into the `OSC UDP TX IP Address` field.

<a name="udp-stamp-settings"></a>
### Stamp Settings

1. Input the IP address of the primary eos console acting as the "Master". 

2. Uncheck `Connect via TCP`

3. Input the receive port you set for eos as the transmit port for the connection.

4. Input the transmit port you set for eos as the receive port for the connection. 

4. Click `Save`

```note
Note: Make sure to swap the transmit and receive port numbers between the eos console and the connection in Stamp. It is a common mistake to have the port numbers for both transmit and receive as the same.
```

---
<a name="eos-cue-lists"></a>
## Cue Lists
An eos family connection can either listen and log cues fired from all cue lists or a selection. The input for multiple lists should be separated by a comma.
For example, to listen and log cues that are from cue lists 1, 2 and 999:
```stamp
1,2,999
```  

---
<a name="eos-leading"></a>
## Cue Stamp Leading
When leading is toggled on at the connection, cues fired from an eos console will trigger an attempt to lead to an <a href="/docs/type"><b>eos stamp</b></a> previously made by a eos family connection. This functionality is useful for running over a section that has previously been recorded. Perhaps during a notes section after a dress rehearsal. This allows for the lighting programmer to remain at the lighting console, to run a cue and lead the media back to the point in time the cue was logged within Stamp during the dress rehearsal. 

There are occasions when a recording has been made where an eos console has not been involved such as within the rehearsal room, typically by a Lighting Designer. In these occasion <a href="/docs/type"><b>cue stamps</b></a> have been made to mark points in time when a cue should sit and usually a rough cue list is created. It is then useful whilst in a technical rehearsal to look back at a rehearsal room run through using the cues that are recorded in the eos console to lead the media.

To alter the type of stamp from eos to cue that the connection attempts to lead to `Lead to Cue Stamps` should be checked.
