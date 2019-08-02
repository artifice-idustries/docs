# Search

- [Basic Searching](#basic-searching)
    - [Text](#text)
    - [Session](#session)
- [Key Words](#key-words)
    - [Type](#type)
    - [Colours](#colour)
    - [Assignment](#assignment)
- [Wildcard Comparisons](#wildcard-comparisons)
	- [Variables](#variables)
    - [Operators](#operators)


Search provides a means to filter the central display to a selection of stamps, that fits your criteria, to better navigate the timeline.
To create a search one or more different types of searches can be combined to predicate against, providing a very simple and expressive method of defining search criteria.
For example, to filter the timeline to display all Cue Stamps labeled and set to be a snap blackout:

`/cue blackout /cue/upTime==0 /cue/downTime==0`

To select the search field, use the keyboard shortcut ⌘ | Ctrl F and begin typing.

<a name="basic-searching"></a>
## Basic Searching

<a name="text"></a>
### Text
The most basic Stamp search accepts text and compares whether the following attributes of a stamp contain it:
- `Session - Title`
- `Flag Stamp - Title`
- `Note Stamp - Label`
- `Cue Stamp - Label`
- `Eos Stamp - Label`
- `Disguise Stamp - Section Name`
<a name="session"></a>
### Session

<a name="type"></a>
### Type
- `/session`
- `/flag`
- `/timecode`
- `/note`
- `/cue`
- `/osc`
- `/midi`
- `/serial`
- `/eos`
- `/qlab`
- `/disguise`
- `/mitti`
- `/hog`

- `/edit`
    flag, note and cue stamps
- `/connection`
    timecode, osc, midi, serial, eos, qlab, disguise, mitti and hog stamps
<a name="colour"></a>
### Colour
- `/green`
- `/red`
- `/yellow`
- `/purple`
<a name="assinnment"></a>
### Assignment
 `@person`
 `@everyone`
 `@team`
 `@categories`
<a name="wildcard-comparisons"></a>
## Wildcard Comparisons
<a name="variables"></a>
### Variables
- `/eos/list`
- `/eos/number`
- `/qlab/number`
- `/hog/list`
- `/hog/number`
- `/cue/number`
- `/cue/upTime`
- `/cue/downTime`
<a name="operators"></a>
### Operators
- `==` - Equals
- `!=` - Not equals
- `<=` - Less than or equals
- `>=` - Greaten than or equals
- `<` - Less than
- `>` - Greater than