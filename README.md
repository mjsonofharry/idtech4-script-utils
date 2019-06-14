# idtech4-script-utils

## Usage

### Imports

Add the following lines to your main script (e.g. doom_main.script):

```
#include "script/string.script"
#include "script/array.script"
#include "script/list.script"
```

Please note that array.script must be imported after string.script.

### Data Structures

#### Array

An array is a `string` type that stores comma-separated values. Arrays are immutable. The max length of an array is 128 characters. Empty strings and commas are considered illegal. All data types must be encoded as strings in order to be stored in the array; this may lead to increased memory usage.

#### List

A list is a `string` type containing a partial reference to a persistent argument. The list functions link persistent arguments together into a sequence of nodes. Lists are mutable. Furthermore, they must be garbage collected and they can only exist at the global scope. However, they have no known size restrictions.

### Functions

#### String

Find the first occurance of a substring starting from a given position:

`float strFindFrom( string text, string search, float offset )`

Find the first occurance of a substring starting from the beginning:

`float strFind( string text, string search )`

Get any and all digits from the right side of a string ('.' counts as a digit):

`string strRightDigits( string text )`

#### Array

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

Remove the element at a particular index of an array:

`string arrayRemove( string array, float idx )`

#### List

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
