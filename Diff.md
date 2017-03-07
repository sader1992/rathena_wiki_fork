# Diff files
A diff file is a file to make:

* Implementation of a modification easier
* Check what and where you modified things
* Share your modifications with the rest of the world
* It is also an easy way for people that give support on forums to check themselves what is wrong to the modifications you made

## Creating .diff files using the tortoise menu
1.  right click on the folder
2.  goto TortoiseSVN menu
3.  click create patch
4.  save as .diff file

Manually Creating .diff files (knowing the mechanics and repairing .diffs if needed)
------------------------------------------------------------------------------------

1.  create a new txt file
2.  rename the .txt extention to .diff
3.  start with pointing out the index (path where the diff files will patch)
    -   example: `Index: src`

4.  add a ========================================= line to indicate the next file
    -   example: `=========================================`

5.  add the patch of the file where content will be removed (---) and add the revision
    -   example: `--- src/common/mmo.c (revision 12300 Stable)`

6.  add the path of the file where content will be added (+++) and add (working copy)
    -   example: `+++ src/common/mmo.c (working copy)`

7.  add the location of the lines that need to be modified in this way:
    1.  `@@`
    2.  `-100`: start reading original lines at line 100
    3.  `,5`: read 5 original lines
    4.  `+100`: start reading new lines at line 100
    5.  `,7`: read 7 new lines
    6.  `@@`

    -   example: `@@ -100,5 +100,7 @@`

8.  add a <space> and write a line that is from the original text (this line will be unmodified) and all others starting with a space
    -   **A SPACE IS NEEDED, IF YOU COPY A DIFF FROM A FORUM APPLY THE SPACES YOURSELF**
    -   example: ` this line will be unmodified`

9.  add a "-" and write the line that must be modified
    -   example: `-this line will be removed from the original code`

10. add a "+" and write the line that need to be placed to replace or added to the original code
    -   example:`+this line will be added in the new code`
        -   full example:
```
on a `@@ -x,7 +x,8 @@`
this line will be unmodified
 this line will be unmodified 
-this line will be deleted 
+this line will replace line 3 
+this line will add a line of code 
 this line will be unmodified, but will move down one line 
 
 this line will be unmodified, move down one line (same as the line above since an <enter> counts as a line)

```

** NOTICE THE <enter> ON LINE 7 MUST START WITH A <space> as well **

## Using .diff/.patch files to patch your server

### Windows
1.  Go to the root folder
2.  Right click the \*.diff file and go to TortoiseGIT menu
3.  Click patch

### Linux
`cd /path/to/your/server/folder`

`patch -p0 < /path/to/patch/file/filename.extension`

## Example of a .diff file
```
Index: map/clif.c
===================================================================
--- map/clif.c  (revision 13318)
+++ map/clif.c  (working copy)
@@ -6745,7 +6745,7 @@
/*==========================================
 * Marry [DracoRPG]
 *------------------------------------------*/
-   void clif_marriage_process(struct map_session_data *sd)
+   /*void clif_marriage_process(struct map_session_data *sd)
    {
        int fd;
        nullpo_retv(sd);
@@ -6755,8 +6755,8 @@
        WFIFOW(fd,0)=0x1e4;
        WFIFOSET(fd,packet_len(0x1e4));
    }
+   */
-   
/*==========================================
 * Notice of divorce
 *------------------------------------------*/
Index: map/clif.h
===================================================================
--- map/clif.h  (revision 13318)
+++ map/clif.h  (working copy)
@@ -53,8 +53,8 @@
     #endif
     
// packet DB
-#define MAX_PACKET_DB      0x400
-#define MAX_PACKET_VER     22
+#define MAX_PACKET_DB      0x500
+#define MAX_PACKET_VER     23
     
     struct s_packet_db {
        short len;
```
