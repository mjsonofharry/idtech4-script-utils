# idtech4-script-utils

## Usage

### Importing the library

Add the following lines to your main script (e.g. doom_main.script):

```
#include "script/string.script"
#include "script/array.script"
#include "script/list.script"
```

Please note that string.script must be imported before array.script.

### Understanding the data structures

#### Array

An array is a `string` type that stores comma-separated values. Arrays are immutable. The max length of an array is 128 characters. Empty strings and commas are considered illegal. All data types must be encoded as strings in order to be stored in the array; this may lead to increased memory usage.

The following are examples of arrays:

`"monster_demon_imp_534,monster_demon_imp_535,monster_demon_imp_536"`

If elements have a common prefix then consider omitting the prefix to save space:

`"534,535,536,537,538,339,540,541"`

Elements can be decimals:

`"123.4,273.5,90.2"`

Or mixed types:

`"test1,test2,35.2,x"`

#### List

A list is a `string` type containing the unique name or ID of a list. The list functions work by linking persistent arguments together into sequences of nodes. Lists are mutable. Furthermore, they must be garbage collected, and they can only exist at the global scope. However, they have no known size restrictions.

The list name will be combined with an integer suffix to generate references to all of the nodes in the list. For example, you might define your list as follows:

`string list = "entity_list";`

The first node will be identified `entity_list_0`, the second `entity_list_1`, the third `entity_list_2`, and so on. These nodes are persistent arguments, which means any entity may access them. Thus, it's important to ensure that you come up with unique names for your lists.

### Function Reference

#### String Functions

Find the first occurance of a substring starting from a given position:

`float strFindFrom( string text, string search, float offset )`

Find the first occurance of a substring starting from the beginning:

`float strFind( string text, string search )`

Get any and all digits from the right side of a string ('.' counts as a digit):

`string strRightDigits( string text )`

#### Array Functions

Get the first element of an array:

`string arrayHead( string array )`

Get every element except for the first in an array:

`string arrayTail( string array )`

Create a new array or add a value to an existing array:

`string arrayAppend( string array, string val )`

Retrieve the element at a particular index of an array:

`string arrayGet( string array, float idx )`

Get the number of elements in the array:

`float arraySize( string array )`

Get the index of a particular element in the array:

`float arrayFind( string array, string val )`

Get every element of the array except for the element at a particular index:

`string arrayRemove( string array, float idx )`

#### List Functions

Create a new list or add an element to an existing list:

`string listAppend( string listName, string val )`

Retrieve the element at a particular index of a list:

`string listGet( string listName, float idx )`

Get the number of elements in the list:

`float listSize( string listName )`

Get the index of a particular element in the list:

`float listFind( string listName, string val )`

Remove all elements from the list:

`float listClear( string listName )`

## Testing

Add these additional scripts:
```
#include "script/testingcore.script"
#include "script/stringspec.script"
#include "script/arrayspec.script"
#include "script/listspec.script"
```

Next, add one or more of the following lines to your main function (e.g. `doom_main()`):

```
stringSpecMain();
arraySpecMain();
listSpecMain();
```

Finally, launch the game, load a map, and check the console. You may have to scroll up to see the test results.
