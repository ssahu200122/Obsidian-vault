# Heading 1
## Heading 2
### Heading 3

**Bold**
*italix*

- jkfaf
- kjkdjaf
- dfkkjaf
- jflaj
	- njdf
	- lkdfjlf

1. fffffff
2. fdfd
3. dfdf
4. daf



==Highlited==
~~Strikethrough~~
- [ ] djnfksf 
- [ ] fglfgf
- [ ] dfdf
- [ ] dffd
- [ ] dfdf'

```
import subprocess

def command(cmd):
	try:
		subprocess.run([cmd],shell=True)
	catch Exception as e:
		print("Error: ",e) 

command("cd new")
```
 
## callouts
1. 
>[!note] 
>ABCD

2.  
 >[!info]
 >ABCD

3.   
   >[!todo] 
   >ABCD

4. 
>[!tip]
>BACD


5. 
>[!question]-
>This is a foldable question, can + and - with callout to set default fold status.

> [!question] Can callouts be nested?
> > [!todo] Yes!, they can.
> > > [!example]  You can even use multiple layers of nesting.


6. 
>[!warning]
>This is my warning

7. 
>[!abstract]
>This text is absyract



<iframe src="https://help.obsidian.md/callouts"  height="1600"></iframe>
