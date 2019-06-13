# idtech4-script-utils

## Using

Add the following lines to your main script (e.g. doom_main.script):

```
#include "script/array.script"
#include "script/list.script"
#include "script/hacky_random.script"
```

## Testing

Add this additional script:
```
#include "script/testingcore.script"
#include "script/arrayspec.script"
#include "script/listspec.script"
```

Next, add this to the main function (e.g. `doom_main()`):
```
	arraySpecMain();
	listSpecMain();
```
Finally, launch the game, load a map, and check the console. You may have to scroll up to see the test results.
