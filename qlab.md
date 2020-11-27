# QLab Connection

- [Introduction](#qlab-introduction)
- [QLab Settings](#qlab-settings)
- [Stamp Settings](#stamp-settings)
    
---
<a name="qlab-introduction"></a>
## Introduction

The QLab connection logs cue methods fired by Figure 53's QLab software creating <a href="/docs/type"><b>qlab stamps</b></a> whenever an OSC address pattern prefixed with `/cue/` is received. A QLab connection utilises the OSC API provided by Figure 53 and requires setup within QLab for messages to be successfully sent to Stamp. Whilst working with a QLab connection we recommend you also refer to Figure 53's <a href="https://qlab.app/docs/v4/scripting/osc-dictionary-v4/"><b>OSC Dictionary</b></a>, specifically the Cue methods section.

When a QLab connection receives a cue method from QLab it will create a <a href="/docs/type"><b>QLab stamp</b></a> and record any of the accompanying parameters.

```note
Note: Currently QLab does not explicitly send updates for cues starting and requires you to create Network Cues for each cue that you would like logged by Stamp. 
```
An example workaround to this problem takes advantage of QLab's OSC Queries API and assignable hotkeys and is shown by Sound Designer, Matt Padden, in this <a href="http://artificers.io/apps/stampv2/Cue Logger.qlab4"><b>QLab file</b></a>.


---
<a name="qlab-settings"></a>
### QLab Settings
1. From the Workspace Settings navigate your way to the Network Settings and create a new patch with the destination set to the IP address of the mac running Stamp with a port number of your choice e.g 4001.

2. In the workspace, create a network cue, then navigate your way to the Settings of that cue, set the destination to be the patch you just made and change the type to QLab message.

3. Choose any command, cue number and parameters you desire.

<a name="stamp-settings"></a>
### Stamp Settings
1. Input the IP address of the mac running QLab. 

2. Input the patch port number you set in QLab as the receive port for the connection.

3. Click `Save`

---

```legal
Figure 53® and QLab® are registered trademarks of Figure 53, LLC. Artifice Industries Ltd. is not affiliated with with Figure 53, LLC and this documentation has not been reviewed nor is it approved by Figure 53, LLC
```

