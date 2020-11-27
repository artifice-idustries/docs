# Search

- [Introduction](#search-introduction)
- [Basic Searching](#basic-searching)
    - [Text](#text)
    - [Session](#session)
- [Keywords](#keywords)
    - [Type](#type)
    - [Colour](#colour)
- [Assignment](#assignment)
- [Wildcard Comparison](#wildcard-comparison)
	- [Variables](#variables)
    - [Operators](#operators)

---
<a name="search-introduction"></a>
## Introduction

Search provides a means to filter the central display to a selection of stamps to better refine the timeline to your current task.
To create a search, one or more different type of searches can be combined to predicate on, providing a very simple and expressive method of defining search criteria. For example, to filter the timeline to display all cue stamps labeled and set to be a snap blackout:
```stamp
/cue blackout /cue/upTime==0 /cue/downTime==0
```
To quickly select the search field, use the keyboard shortcut `Option` `⌘` `J` and begin typing.

---
<a name="basic-searching"></a>
## Basic Searching

<a name="text"></a>
### Text
The most basic Stamp search accepts text and compares the following attributes of a stamp on it. Text searches are case and diacritic insensitive.

The following attributes of each stamp is predicated on the text: `session.title`, `flag.title`, `note.label`, `cue.label`, `cue.number`, `eos.label`, `eos.cueNumber`, `hog.cueNumber`, `qlab.cueNumber` and `disguise.sectionName`.

<a name="session"></a>
### Session
Sessions are used to organise the timeline into periods of time. 
To filter the timeline to show all stamps within a session; a "Session Search" can be built by using the desired session's title enclosed by `` ` ``. For example:
```stamp
`Start of Day 1`
```

---
<a name="keywords"></a>
## Keywords
Specific words prefixed with `/` can be used to allow for quick generalised searching.
<a name="type"></a>
### Type
Every stamp created has a <a href="/docs/type"><b>Type</b></a> property.
To filter the central display to include stamps of a certain type, use the following keywords:

[`/session`](/docs/type/#session-type)
[`/flag`](#flag-type)
[`/timecode`](#timecode-type)
[`/note`](#note-type)
[`/cue`](#cue-type)
[`/osc`](#osc-type)
[`/midi`](#midi-type)
[`/serial`](#serial-type)
[`/eos`](#eos-type)
[`/qlab`](#qlab-type)
[`/disguise`](#disguise-type)
[`/mitti`](#mitti-type)
[`/hog`](#hog-type)

#### Special Type Keywords
#### <a name="edit-keyword">`/edit`</a>

The `/edit` keyword filters the cetral display to include stamps that are editable.

```note
Note: "/edit" is the equivilent of "/flag /note /cue".
```

#### <a name="connection-keyword">`/connection`</a>

The `/connection` keyword filters the central display to include stamps that are made from a connection.

```note
Note: "/connection" is the equivilent of "/timecode /osc /midi /serial /eos /qlab /disguise /mitti /hog".
```
<a name="colour"></a>
### Colour
Each Stamp has a colour property. To filter the central display to include the stamps with a specific colour, use the following keywords:

[`/green`](#green-colour)
[`/red`](#red-colour)
[`/yellow`](#yellow-colour)
[`/purple`](#purple-colour)

<a name="assinnment"></a>
## Assignment
Stamps can be asssigned to team members or categories. 
Use the name of a person or category prefixed by an `@` symbol to filter the central display to include stamps assigned to them.
#### <a name="#person-assingment">`@person`</a>

The `@person` wildcard will predicate on the first, last or company name associated with the team member and filter the central display to include the result.

```stamp
@Sam @Smallman @artificers
```
#### <a name="#category-assingment">`@category`</a>

The `@category` wildcard will predicate on the category name associated with the category and filter the central display to include the result.
```stamp
@Lighting @Sound @Automation
```
### Special Assignment Keywords

#### <a name="#team-assingment">`@team`</a>
The `@team` keyword filters the central display to include stamps that are assigned to a person.

#### <a name="#categories-assingment">`@categories`</a>
The `@categories` keyword filters the central display to include stamps that are assigned to a category.


#### <a name="everyone-assingment">`@everyone`</a>
The `@everyone` keyword flters the central display to include stamps that are assigned to either a person or a category.

```note
Note: "@everyone" is the equivilent of "@team @categories".
```

---
<a name="wildcard-comparison"></a>
## Wildcard Comparison
To allow for expressive and scalable searching, wildcards can be utilised in conjuction with relational operators.
For example, to filter the timeline to display all Cue Stamps with a number greater than or equal to 10:
```stamp
/cue/number>=10
```

<a name="variables"></a>
### Variables
[`/cue/number`](#cue-number-variables)
[`/cue/upTime`](#cue-uptime-variables)
[`/cue/downTime`](#cue-downtime-variables)
[`/eos/list`](#eos-list-variables)
[`/eos/number`](#eos-number-varibales)
[`/qlab/number`](#qlab-number-variables)
[`/hog/list`](#hog-list-variables)
[`/hog/number`](#hog-number-variables)

<a name="operators"></a>
### Operators
[`==`](#equals-operator)
[`!=`](#not-equals-operator)
[`<=`](#less-than-or-equals-to-operator)
[`>=`](#greater-than-or-equals-to-operator)
[`<`](#less-than-operator)
[`>`](#greater=than-operator)

#### <a id="equals-operator">`==` Equals to</a>
The `==` operator can be used to compare if a stamps property is equal to a given value and filters the central display to include the results.
```swift
/cue/number==1
```
This search would filter the central display to include all cue stamps that have their `cue.number` property set to `1`.

#### <a id="not-equals-operator">`!=` Not Equals to</a>
The `!=` operator can be used to filter out and not include stamps in the central display.
```swift
/eos/list!=2
```
This search would filter the central display to not include any eos stamps with their `eos.list` property set to `2`.

#### <a id="less-than-or-equals-to-operator">`<=` Less Than or Equals to</a>
The `<=` operator can be used to compare if a stamps property is less than or equal to a given value and filters the central display to include the results.
```swift
/cue/number<=50
```
This search would filter the central display to include any cue stamps with their `cue.number` property set to anywhere below and including `50`. For example you may want to see all your cue stamps for Act 1 of the production and the cue number for the interval is `50`.

#### <a id="greater-than-or-equals-to-operator">`>=` Greaten Than or Equals to</a>
The `>=` operator can be used to compare if a stamps property is greater than or equal to a given value and filters the central display to include the results.
```swift
/cue/number>=51
```
This search would filter the central display to include any cue stamps with their `cue.number` property set to anywhere above and including `51`. For example you may want to see all your cue stamps for Act 2 of the production and the cue number for ending the interval is `51`.

#### <a id="less-than-operator">`<` Less Than</a>
The `<` operator can be used to compare if a stamps property is less than a given value and filters the central display to include the results.
```swift
/cue/number<10
```
This search would filter the central display to include any cue stamps with their `cue.number` property set to anywhere below `10`. For example you may want to see all your cue stamps for the opening sequence of the production which ends at cue `9`.

#### <a id="greater=than-operator">`>` Greater Than</a>
The `>` operator can be used to compare if a stamps property is greater than a given value and filters the central display to include the results.
```swift
/cue/number>999
```
This search would filter the central display to include any cue stamps with their `cue.number` property set to anywhere greater than `999`. For example you may want to see all your cue stamps that deal with the rig check of the production which starts at cue `1000`.
