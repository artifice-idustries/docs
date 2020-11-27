# Find

- [Introduction](#search-introduction)

---
<a name="search-introduction"></a>
## Introduction

Find provides a means to locate a stamp in the central display. To find a stamp, one or more different types of <a href="/docs/search"><b>Search</b></a> can be combined to predicate on, providing a very simple and expressive method of defining search criteria and locating a stamp.
For example, to find all cue stamps labeled and set to be a snap blackout in the timeline:
```stamp
/cue blackout /cue/upTime==0 /cue/downTime==0
```
To quickly select the find field, use the keyboard shortcut `⌘` `F` and begin typing.

The total amount of found stamps will update as you type into the find field. You can then use the buttons marked `<` and `>` to cycle through the found stamps.

```note
Note: Find uses the exact same syntax as Search.
```