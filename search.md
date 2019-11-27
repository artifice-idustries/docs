# Search

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

Search provides a means to filter the central display to a selection of stamps to better refine the timeline to your current task.
To create a search, one or more different type of searches can be combined to predicate against, providing a very simple and expressive method of defining search criteria.
For example, to filter the timeline to display all cue stamps labeled and set to be a snap blackout:

`/cue blackout /cue/upTime==0 /cue/downTime==0`

To quickly select the search field, use the keyboard shortcut `Option` `⌘` `J` and begin typing.

<a name="basic-searching"></a>
## Basic Searching

<a name="text"></a>
### Text
The most basic Stamp search accepts text and compares the following attributes of a stamp against it:
- Session **title** *containing* **text**
- Flag Stamp **title** *containing* **text**
- Note Stamp **label** *containing* **text**
- Cue Stamp **label** *containing* **text**
- Cue Stamp **number** *equals to* **text**
- Eos Stamp **label** *containing* **text**
- Eos Stamp **cue number** *equals to* **text**
- Hog4 Stamp **cue number** *equals to* **text**
- QLab Stamp **cue number** *equals to* **text**
- Disguise Stamp **section name** *containing* **text**

Text searches are case and diacritic insensitive.

<a name="session"></a>
### Session
Sessions are used to organise the timeline into periods of time. 
To filter the timeline to show all stamps within a session; a `Session Search` can be built by using the desired session's title enclosed by `\``.
For example:

`\`Start of Day 1\``

<a name="keywords"></a>
## Keywords
Specific words prefixed with `/` can be used to allow for quick generalised searching.
<a name="type"></a>
### Type
Every stamp created has a `type` property.
To filter the timeline to show all the stamps of a certain type, use the following keywords:
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

#### Special Type Keywords
- `/edit` - Filter to stamps that are editable.

    This search is the equivilent of `/flag /note /cue`
    
- `/connection` - Filter to stamps that are made from a connection.

    This search is the equivilent of `/timecode /osc /midi /serial /eos /qlab /disguise /mitti /hog`

<a name="colour"></a>
Each Stamp has a colour property. To filter the timeline to show all the stamps with a specific colour, use the following keywords:
### Colour
- `/green`
- `/red`
- `/yellow`
- `/purple`

<a name="assinnment"></a>
## Assignment
Stamps can be asssigned to team members or categories. 
Use the name of a person or category prefixed by an `@` symbol to filter the timeline to stamps assigned to them.
- `@person` e.g. @Sam, @Smallman or @artificers

	This search will predicate against the first, last or company name associated with the team member.

- `@category` e.g. @Developer

### Special Assignment Keywords
- `@team` - Filter to stamps that are assinged to a person.
- `@categories` - Filter to stamps that are assinged to a category.
- `@everyone` - Filter to stamps that are assigned to either a person or a category.

<a name="wildcard-comparison"></a>
## Wildcard Comparison
To allow for expressive and scalable searching, wildcards can be utilised in conjuction with relational operators.
For example, to filter the timeline to display all Cue Stamps with a number greater than or equal to 10:

`/cue/number>=10`

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
- `!=` - Not equals to
- `<=` - Less than or equals to
- `>=` - Greaten than or equals to
- `<` - Less than
- `>` - Greater than
