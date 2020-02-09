# Eos

Eos Family Devices have the ability to send a wealth of information through the popular "protocol" Open Sound Control.

## Setup
Establish whether you want to connect Stamp and your Eos Family Device over a UDP or TCP Connection.

## Eos Settings

In `ECU>Settings>Network>Interface Protocols`: 
- set the OSC TCP format to 1.1 (TCP Only) and Enable UDP Strings & OSC

In `Displays>Setup>Show>Show Control`:
- Enable "String RX".
- Enable "String and OSC TX".
- Set the OSC TX IP Address to the same as the computer’s IP Address running Stamp (UDP Only).
- Set the OSC TX Port Number to be the same as the Receive Port of the connection in Stamp(UDP Only).
- Set the OSC RX Port Number to be the same as the Transmit Port of the connection in Stamp (UDP Only).

## Stamp Settings

- Open the Utilities Tab.
- Select Connections.
- Add an Eos Family Connection from the Pull Down Menu.
- Edit the connection by Double Clicking on it.
- Give your connection a recognisable Name.
- Set the IP Address to the same as the Eos Family Device.
- Select whether your connection works over UDP or TCP.
- Set the Transmit Port to be the same as the OSC RX Port Number of the Eos Family device (UDP Only)
- Set the Receive Port to be the same as the OSC TX Port Number of the Eos Family device. (UDP Only)
- Set whether your connection listens to messages from All Cue Lists or a selection of Specific Cue Lists.
- Click Save.
- Click Connect on your connection