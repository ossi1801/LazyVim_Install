# Good to know Vim commands

### 1. Replace All :
##### Find each occurrence of 'foo' (in all lines), and replace it with 'bar'.
```
:%s/foo/bar/g
```
#### For specific lines:
```
:6,10s/foo/bar/g
```
[source](https://stackoverflow.com/questions/19994922/find-and-replace-strings-in-vim-on-multiple-lines)
---

### 2. Apply an expression with "normal" keyword :
##### Select an area with visual mode first, then press colon ( : )
##### Below will show if done correctly 
```
'<,'>
```
##### Then in command mode type normal with expression after it
```
normal Iprint("
```
##### This will insert  print("  to the beginning of the lines of which you selected 

##### And if you reselect the rows you can use A to append to end
```
normal A");
```
##### This has now wrapped your selected rows in: print("yourtexthere");
---
### 3. Search (normal mode):
##### Find each occurrence of 'foo' (in all lines)
```
/foo
```
#### To go next:
```
n
```
#### To go Previous:
```
N
```
---
### 4. Recording macro and registers (:reg)
##### Press q to record next key will the buffer where it will be place for ex a (qa)
##### Below will show if done correctly 
```
recording @a
```
###### Note you can also check your register by typing :reg  You can quit the register buffer normally :q
##### Then do your macro, when finished press q again.

#### To repeat your macro press @a
```
@a
```
##### You can also press @@ for last macro
##### or for ex. 5@@ to repeat the last used macro 5 times
---
### 5. Replace with an expression using "s" keyword using capture groups:
##### Select an area with visual mode first, then press colon ( : )
##### Below will show if done correctly 
```
'<,'>
```
##### Capture group (separated by whitespace) 
```
\(.*\)
```
##### Now that you know the syntax for a capture group, you can use it with:  \1
```
s/printf("\(.*\)".*/CustomPrint\(\1);
```
#### Replaces printf("Hello World"); with CustomPrint(Hello World);
##### Forward slashes (/) usually means start and backslashes (\\) escape invalid chars in expression. In this case parantheses \( .
##### The other .* (not capture group) just extends the selection to the end of line
##### So in plaint text it reads: 
```
REPLACE ROW(S) printf("TEXT" until_end_of_this_line
WITH CustomPrint(TEXT);
```
