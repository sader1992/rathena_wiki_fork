This article will, in the end, contain all possible script related errors, what their causes are and what you should do to fix them.

Introduction
------------

### Definition of Error

The errors mentioned in this article, are all the possible script related errors that show in the map-server's console. These errors are often accompanied by a tag in front of it. The tag will be \[Error\] or \[Fatal Error\]. (Where fatal error will crash your server.) Also, the errors that display a part of a script with \*'s in front of it (Parsing Errors), will be covered in this article. Please do note that you must be in debugging mode, which is if I'm not mistaking, the default mode. This article will not cover the different kinds of script related warnings, because the error-list alone is already massive.

### How to Find and Fix Your Error

Fixing errors in scripts require some handiness. Single errors are easy to do, but sometimes, you get a lot of errors. Do not be afraid then though, because a large list of errors will often be fixed, by fixing the first error. So, when using this guide, search for the topmost error in your server's console first, and try to fix it. If it is fixed, there is a 50% chance that all the other errors will disappear.

Sometimes though, the amount of errors are so huge, that you cannot scroll high enough to find the first error. If this is the case, then there are three ways to make it easier for you:

-   Fetch the error stream and save it to a file
-   Comment out the newly added NPCs, or only make the newly added NPCs load.
-   Divide your NPCs into smaller NPCs.

How to do the first, I am afraid to say, I forgot. The second one is fairly easy though. Removing your new scripts from the conf files, and starting up your server then, will tell you where to look. If the errors are gone, then they are most likely in your new scripts. Otherwise, they are in the default scripts. If they are in your new scripts, then it is wise to first read to that script again, to remove obvious errors. Also, always check the header. If you make a single mistake in the header, the rest of the script will bug out. If that still doesn't help, decrease the error list, then consider to have your server only load the new scripts, one at the time, in the hope that it will show fewer errors.

However, if that still doesn't allow you to find the topmost error, then there is always the third option - breaking down your script in smaller NPCs. What this means, is that you just randomly put inside your script a } followed by a valid header. Then you've split your script in two halves. 50% chance that 50% of the errors will be gone, and that you are closer to finding the solution. If the error list is still too long, simply split it up again, and again, and again, until you can see all the errors of a single NPC in your screen. That way, you can find the first error in that specific NPC, and fix it. This will result into the mapserver only showing the errors in the broken down NPCs before that NPC. I know, it's a long method, but sometimes, it's the only way. But when you have found the original error, then you can use this guide to find a solution for it.

Each error will have it's own section, in which the exact error is listed. These sections will also contain an explanation on what likely caused this error and what possible fixes are. This all is accompanied by one or more examples, to make everything more clear. To quickly find your specific error, search for a part of the error message, of course, without the Error tag. When searching for it, make sure that you do not include the things that can alter, like NPC name, file name, variable name etc.

If the error you want to search for, almost completely contains custom things, like that NPC name etc, and you still want to look for it, then try replacing all the parts that can change by three dots. For example if you want to search for this error:

`Out of range spawn coordinates: prt_fild08 (-50,-50), map size is (250,250) `

then try using this to search for:

`Out of range spawn coordinates: ... (...,...), map size is (...,...) `

If this still doesn't give any results, you can always try the main index list. However, older error lines do not show up in this one. So, if you are also unsuccessful there, then please try the [Outdated Errors](/#Outdated_Errors "wikilink") section as a last resort. It lists all old error message. If you still cannot find it, then you can always try the Scripting Support forum.

### Using Older SVN Revisions

You are probably not using the latest version of rAthena. Unfortunately, over time, some errors change in text, or even become obsolete (erased). To not put you in a disadvantage, we will keep track of older error reports. At the moment, we have up to Revision 12340 covered for the script.c related errors, and up to 11501 covered for npc.c related errors.

When time comes, we will try to cover even older errors, and change the list if new errors appear, or when they change in syntax. However, if the error that you are looking for, is not in the normal list, nor the Outdated Errors list, then your best chance is asking for support in the Script Support Forum on the forums. Please, do not forget to mention your SVN revision when doing this.

Overview of Errors
------------------

There is a total of over 152 errors at the moment. Currently, 152 of them are covered. This is 100.00% of the total for the script.c section and an unknown percentage for the npc.c section.

### Outdated Errors

This list contains all currently known old errors messages that have been changed. They will link you to the current version of the error.

#### Up to Revision 10812

------------------------------------------------------------------------

-   [buildin_guardian: invalid data type for argument \#8 (...).](/Overview_of_Errors#script:guardian:_invalid_data_type_for_argument_.236_.28from_1.29 "wikilink")
-   [buildin_input: given argument is not a variable!](/Overview_of_Errors#script:input:_not_a_variable_script: "wikilink")
-   [script: buildin_set: not name](/Overview_of_Errors#script:set:_not_a_variable "wikilink")
-   [script: callsub: not label !](/Overview_of_Errors#script:callsub:_argument_is_not_a_label "wikilink")
-   [getvariableofnpc: can't find npc ...](/Overview_of_Errors#script:getvariableofnpc:_can.27t_find_npc_..._script: "wikilink")
-   [script: getvariableofnpc: first argument is not a variable name](/Overview_of_Errors#script:getvariableofnpc:_not_a_variable "wikilink")
-   [script: getvariableofnpc: invalid scope ... (not npc variable)](/Overview_of_Errors#script:getvariableofnpc:_invalid_scope_.28not_npc_variable.29 "wikilink")
-   [script:goto: not label!](/Overview_of_Errors#script:goto:_not_a_label "wikilink")
-   [script:menu: argument \#... (from 1) is not a label or label not found (op=...).](/Overview_of_Errors#script:menu:_argument_.23..._.28from_1.29_is_not_a_label_or_label_not_found. "wikilink")
-   [script:menu: argument \#... (from 1) is not a string or compatible (op=...).](/Overview_of_Errors#script:menu:_argument_.23..._.28from_1.29_is_not_a_string_or_compatible. "wikilink")
-   [script:op_1: invalid type of data op:... data:...](/Overview_of_Errors#script:op_1:_argument_is_not_a_number_.28op.3D....29 "wikilink")
-   [script:op_1: unexpected operator op:...](/Overview_of_Errors#script:op_1:_unexpected_operator_..._i1.3D... "wikilink")
-   [script:op_2: invalid type of data op:... left:... right:...](/Overview_of_Errors#script:op_2:_invalid_data_for_operator_... "wikilink")
-   [script:op_2num: division by zero detected op:...](/Overview_of_Errors#script:op_2num:_division_by_zero_detected_op.3D..._i1.3D..._i2.3D... "wikilink")
-   [script:op_2num: unexpected number operator op:...](/Overview_of_Errors#script:op_2num:_unexpected_number_operator_..._i1.3D..._i2.3D... "wikilink")
-   [script:op2_str: unexpected string operator op:...](/Overview_of_Errors#script:op2_str:_unexpected_string_operator_... "wikilink")
-   [script:op_3: invalid type of data op:... data:...](/Overview_of_Errors#script:op_3:_invalid_data_for_the_ternary_operator_test "wikilink")
-   [script:warpportal: npc is needed](/Overview_of_Errors#script:warpportal:_npc_is_needed "wikilink")

In-depth Info on Errors
-----------------------

### Warnings (script.c)

Warnings do not necessarily mean, that something is wrong, but can work in an undesired way.

#### Unexpected type for argument ... Expected ...

<u>**Cause**</u>
The data type of the value passed into a build-in function's argument differs from the one defined in that function's BUILDIN_DEF definition, typically passing a number where a string is expected and vice versa. A set of \[Debug\] messages follow this warning, that specify the function's parameters, the function itself and the NPC that hosts the reported script. This warning occurs only during runtime of a script. Note, that the affected script continues to run and auto-conversion rules apply, except the script command itself stops the execution of the script (typically commands that deal with variables and labels).

<u>**Solution**</u>
Verify all values passed to the function and make sure, that all of them have the expected type.

<u>**Example**</u>
[itemheal](/itemheal "wikilink") "200",0; The first parameter is supposed to be a number (amount of HP to heal). So the correct script would be:

`itemheal 200,0;`

### Errors (npc.c)

All errors located in npc.c that have the \[Error\] tag are listed in this section.
==== bad duplicate name (in ...)! : ... ==== Source Syntax: ShowError("bad duplicate name (in %s)! : %s", file, w2);
<b><u>Cause</u></b>
The format of your duplicate line is wrong. What is missing, is either which NPC the duplicate command should copy or the use of an incorrect name or incorrect characters. The error is located in the file that is mentioned between the ( and ). The name that the server found, if any there, is displayed after the <b>:</b>.
<b><u>Solution</u></b>
Make sure that you have put an event label in the duplicate name. The format should be one of the following two:

`map,x,y,d`<tab>`duplicate(EVENT LABEL)`<tab>`New name`<tab>`sprite`
`map,x,y,d`<tab>`duplicate(EVENT LABEL)`<tab>`New name`<tab>`sprite,triggerx,triggery`

<b><u>Example</u></b>
Wrong code:

`prontera,200,200,4`<tab>`script`<tab>`Original::TestNPC`<tab>`46,{`
`   mes "Hi";`
`   close;`
`}`
`prontera,210,200,4`<tab>`duplicate()`<tab>`Copy`<tab>`46`

The last line is missing the event label between the brackets. It should be this:

`prontera,210,200,4`<tab>`duplicate(TestNPC)`<tab>`Copy`<tab>`46`

------------------------------------------------------------------------

#### bad duplicate name (in ...)! (not exist) : ...

Source Syntax: ShowError("bad duplicate name (in %s)! (not exist) : %s\\n", file, srcname);
<b><u>Cause</u></b>
This error is trying to tell you that you are duplicating a non-existing NPC.
<b><u>Solution</u></b>
Make sure that the NPC you want to duplicate, has the same Event Label as you specified between the round brackets behind duplicate. Either correct the Event Label of the original NPC or the Event Label in the duplicate line. Or, erase the duplicate line. Remember, the format for the original NPC is:

`map,x,y,d,`<tab>`script`<tab>`Original Name`<b>`::My_Event_Label`</b><tab>`sprite{,triggerx,triggery},{`

And for the duplicate:

`map,x,y,d,`<tab>`duplicate(`<b>`My_Event_Label`</b>`)`<tab>`New Name`<tab>`sprite{,triggerx,triggery}`

<b><u>Example</u></b>
Wrong code:

`prontera,200,200,4`<tab>`script`<tab>`Original`<tab>`46,{`
`   mes "Hi";`
`   close;`
`}`
`prontera,210,200,4`<tab>`duplicate(TestNPC)`<tab>`Copy`<tab>`46`

The first line is missing the event label between the brackets. It should be this:

`prontera,210,200,4`<tab>`script`<tab>`Original`<b>`::TestNPC`</b><tab>`46`

------------------------------------------------------------------------

#### bad monster ID : ... ... (file ...)

Source Syntax: ShowError("bad monster ID : %s %s (file %s)\\n", w3, w4, current_file);
<b><u>Cause</u></b>
The monster you are trying to spawn, does not exist. At least, the mapserver could not find it's mob_id in mob_db.txt or mob_db2.txt. (Or possibly not in the homunculus db.)
<b><u>Solution</u></b>
Either add the monster to the mob_db2.txt file, or change the mob_id number in the spawn line to the correct mob_id number.
<b><u>Example</u></b>
Wrong code:

`monster "prt_fild08",100,100,"Poring",999,5;`

Correct code:

`monster "prt_fild08",100,100,"Poring",1002,5;`

------------------------------------------------------------------------

#### bad monster line : ... ... ... (file ...)

Source Syntax: ShowError("bad monster line : %s %s %s (file %s)\\n", w1, w3, w4, current_file);
<b><u>Cause</u></b>
For a monster line to be correct, it needs to have at least the following:

-   Valid mapname
-   Valid x
-   Valid y

And it also needs to have at least:

-   Valid class
-   Valid amount

If you only have two or less of the topmost, and/or 1 or less of the bottom two, then this error will occur.
<b><u>Solution</u></b>
Make sure that your monster line contains at least the needed information. Check if you have a mapname, x, y, mob_id and an amount, and correct it where needed.
<b><u>Example</u></b>
Wrong code:

`monster "prt_fild08","Poring",5;`

Correct code:

`monster "prt_fild08",0,0,"Poring",1002,5;`

------------------------------------------------------------------------

#### bad script line (in file ...): ...

Source Syntax: ShowError("bad script line (in file %s): %s\\n", file, w3);
<b><u>Cause</u></b>
This error occurs when the header of your NPC is incorrect. There are two separate ways for a NPC header to function correctly:

`map,x,y,d`<tab>`script`<tab>`Name`<tab>`sprite,{`
`-`<tab>`script`<tab>`Name`<tab>`-1,{`

When the server does not detect a dash (-) at the start of your header, it will check for the other format. If it does not find a mapname, x, y, direction, the word script or a comma after the sprite, then it will give you this error.
<b><u>Solution</u></b>
Recheck, if you abide the rules of writing a NPC header. Make sure you have all the commas in the right spots, that you have the location setup correctly and that you are using the script identifier word.
<b><u>Example</u></b>
Wrong code:

`prontera,200,200`<tab>`script`<tab>`My NPC`<tab>`48,{`

Correct code:

`prontera,200,200,4`<tab>`script`<tab>`My NPC`<tab>`48,{`

------------------------------------------------------------------------

#### Bad setcell line : ...

Source Syntax: ShowError("Bad setcell line : %s\\n",w3);
<b><u>Cause</u></b>
You did not obey the format for using the setcell command. The format should be:

<map name>`%TAB%setcell%TAB%`<type>`,`<x1>`,`<y1>`,`<x2>`,`<y2>

This error occurs when you forgot one of the following five things:

-   Forgot to define the type.
-   Forgot to define x1
-   Forgot to define y1
-   Forgot to define x2
-   Forgot to define y2

<b><u>Solution</u></b>
Recheck, if the way you defined your setcell line is correct. There should be a tab, followed by 5 arguments after the setcell keyword.
<b><u>Example</u></b>
Wrong code:

`prontera`<tab>`setcell`<tab>`cell_wall,170,50,171`

Correct code:

`prontera`<tab>`setcell`<tab>`cell_wall,170,50,171,100`

------------------------------------------------------------------------

#### bad shop line : ...

Source Syntax: ShowError("bad shop line : %s\\n", w3);
<b><u>Cause</u></b>
You did not obey the format of a shop header. Make sure it uses the following format:

`map,x,y,d`<tab>`shop`<tab>`Name`<tab>`sprite,{item list + prices}`

This error occurs when you are missing the mapname, x, y and/or direction.
<b><u>Solution</u></b>
Recheck if you are using the shop header in the correct way. Add the missing mapname, x-coordinate, y-coordinate and/or direction.
<b><u>Example</u></b>
Wrong code:

`prontera,100,100`<tab>`shop`<tab>`My First Shop`<tab>`83,501:-1,502:-1,503:-1,504:-1,506:-1`

Correct code:

`prontera,100,100,4`<tab>`shop`<tab>`My First Shop`<tab>`83,501:-1,502:-1,503:-1,504:-1,506:-1`

------------------------------------------------------------------------

#### bad warp line : ...

Source Syntax: ShowError("bad warp line : %s\\n", w3);
<b><u>Cause</u></b>
You didn't use the warp NPC header correctly. Make sure it uses the following format:

`from_map,from_x,from_y,d`<tab>`warp`<tab>`Name`<tab>`trigger_x,trigger_y,to_map,to_x,to_y`

This error occurs when you are missing one of the parameters given after the name. (Destination map and coordinates and trigger size.)
<b><u>Solution</u></b>
Recheck if you are using the warp header in the correct way. Add what is missing.
<b><u>Example</u></b>
Wrong code:

`prontera,107,215,0`<tab>`warp`<tab>`prt01`<tab>`prt_in,240,139`

Correct code:

`prontera,107,215,0`<tab>`warp`<tab>`prt01`<tab>`2,2,prt_in,240,139`

------------------------------------------------------------------------

#### bad warp line (destination map not found): ...

Source Syntax: ShowError("bad warp line (destination map not found): %s\\n", w3);
<b><u>Cause</u></b>
Your mapserver failed to find the map where the warp is supposed to go to.
<b><u>Solution</u></b>
Make sure that the destination you typed in your warp line, really exists and is a map loaded by the server. Of course, also check it for typos.
<b><u>Example</u></b>
Wrong code:

`prontera,107,215,0`<tab>`warp`<tab>`prt01`<tab>`prontera_in,240,139`

Correct code:

`prontera,107,215,0`<tab>`warp`<tab>`prt01`<tab>`prt_in,240,139`

------------------------------------------------------------------------

#### Could not parse file '...', line '...'. \* ... ... ... ...

Source Syntax: ShowError("Could not parse file '%s', line '%i'.\\n \* %s %s %s %s\\n",current_file,lines,w1,w2,w3,w4);
<b><u>Cause</u></b>
This can mean a lot of things. Please make sure that your header always looks like this:

`map,x,y,d`<tab>`script`<tab>`Name`<tab>`sprite{,triggerx,triggery},{`

The server reads this in in the following manner:

`location_info`<tab>`script`<tab>`Name{#tag}{::EventLabel}`<tab>`other_info`

If you are missing tabs, or any of these four parts, or a combination, then the mapserver will return this error.
<b><u>Solution</u></b>
Check your NPC header, and make sure it abides the rules.
<b><u>Example</u></b>
Wrong code:

`prontera,200,200,4`<space>`My NPC`<tab>`48,{`

Correct code:

`prontera,200,200,4`<tab>`script`<tab>`My NPC`<tab>`48,{`

------------------------------------------------------------------------

#### File not found : ...

Source Syntax: ShowError ("File not found : %s\\n", name);
<b><u>Cause</u></b>
You have added a NPC to the conf file, but the server cannot find the file you mentioned in there.
<b><u>Solution</u></b>
Check if the file that the mapserver reports, actually exists. If it does, make sure you typed the entry in the conf file in a case sensitive way. If the file does not exist, comment out or erase the entry in the conf file.

------------------------------------------------------------------------

#### Invalid map '...' in line ..., file ...

Source Syntax: ShowError("Invalid map '%s' in line %d, file %s\\n", mapname, lines, current_file);
<b><u>Cause</u></b>
This means, that the map which you specified in the header of the script, does not exist. Or at least, the server cannot find it.
<b><u>Solution</u></b>
Recheck if you spelled the name right and if the map does exist on your server (by warping to it).
<b><u>Example</u></b>
Wrong code:

`pront,200,200,4`<tab>`script`<tab>`My NPC`<tab>`48,{`

Correct code:

`prontera,200,200,4`<tab>`script`<tab>`My NPC`<tab>`48,{`

------------------------------------------------------------------------

#### Missing right curly at file ..., line ...

Source Syntax:
ShowError("Missing right curly at file %s, line %d\\n",current_file, \*lines);
ShowError("Missing right curly at file %s, line %d\\n", file, \*lines);
ShowError("Missing right curly at file %s, line %d\\n",file, \*lines);
<b><u>Cause</u></b>
The script that loaded, has more left curly brackets than right curly brackets.
<b><u>Solution</u></b>
Count and check the number and locations of the left and right curly brackets. In a single script, they should be the same amount.

------------------------------------------------------------------------

#### no such shop npc : ...

Source Syntax: ShowError("no such shop npc : %d\\n",id);
<b><u>Cause</u></b>
You tried to call a non-existing shop with the callshop command.
<b><u>Solution</u></b>
Make sure the shop actually exists. Also make sure that it has no sprite (-1) and no location (-) part.

------------------------------------------------------------------------

#### npc_addeventimer: Event ... does not exists.

Source Syntax: ShowError("npc_addeventimer: Event %s does not exists.\\n", name);
<b><u>Cause</u></b>
You tried to use a timer in combination with an Event Label. However, the event label was not found by the mapserver.
<b><u>Solution</u></b>
Make sure that the event label you are referring to exists.
<b><u>Example</u></b>
Wrong code:

<header with the npc name Tirza>
`...`
`addtimer 60000, "Tirza::OnTimeChecker";`
`...`
`OnTimeCheck:`
`...`

Correct code:

<header with the npc name Tirza>
`...`
`addtimer 60000, "Tirza::OnTimeCheck";`
`...`
`OnTimeCheck:`
`...`

------------------------------------------------------------------------

==== npc_click: npc_id != 0 ==== Source Syntax: ShowError("npc_click: npc_id != 0\\n");
<b><u>Cause</u></b>
This error seems to occur when a player uses more than one NPC at the same time. Unlike common sense, this is possible. It can happen when an event is triggered by the player (through a timer for example), and while that code is being executed, the player clicks/starts another NPC.
<b><u>Solution</u></b>
This error is hard to prevent to be honest. You will have to check in some way if there is any way for a player to be using a NPC and at the same time having an event triggered at another NPC.

------------------------------------------------------------------------

#### npc_event: (mob_kill) event not found \[...\]

Source Syntax: ShowError("npc_event: (mob_kill) event not found \[%s\]\\n", mobevent);
<b><u>Cause</u></b>
You created a monster spawn that has an Event Label attached to it (which will trigger when the monster dies). However, the mapserver could not find this event label in your script.
<b><u>Solution</u></b>
Verify that the monster should have an OnDeath-type label, that the Event Label exists, and that you did not make a typo in it.

------------------------------------------------------------------------

#### npc_event: event not found \[...\]

Source Syntax: ShowError("npc_event: event not found \[%s\]\\n", eventname);
<b><u>Cause</u></b>
Kind of the same as the error above. An event label you want to use, does not exist.
<b><u>Solution</u></b>
Verify that the Event Label exists, and that you did not make a typo in it.

------------------------------------------------------------------------

#### npc_parse_script: label name longer than 23 chars! '...' (...)

Source Syntax: ShowError("npc_parse_script: label name longer than 23 chars! '%s'\\n (%s)", lname, current_file);
<b><u>Cause</u></b>
You have created a label (normal or event label) which is longer than 23 characters. The mapserver cannot use labels bigger than that size.
<b><u>Solution</u></b>
Shorten your (event)label until it has 23 or less characters in it.
<b><u>Example</u></b>
Wrong code:

`MyFirstLabelWhichITypedTheDayBeforeYesterday: //44 characters O_O`

Correct code:

`L_MyFirstLabel01: //16 characters.`

------------------------------------------------------------------------

#### npc_script_event: NULL sd. Event Type ...

Source Syntax: ShowError("npc_script_event: NULL sd. Event Type %d\\n", type);
<b><u>Cause</u></b>
Your code triggered an event, which requires a player to be online and attached to the NPC. For some reason, the player isn't there.
<b><u>Solution</u></b>
If it is a player attached timer that causes this, and the player logged off, then there is nothing much you can do. In any other case, make sure that your script has an attached player. (Like using addtimer instead of initnpctimer.)

------------------------------------------------------------------------

#### npc_settimerevent_tick: Attached player not found!

Source Syntax: ShowError("npc_settimerevent_tick: Attached player not found!\\n");
<b><u>Cause</u></b>
Your script, or in this specific case, your timer, used to have a player attached to it. The player went missing though. This is most likely because the player logged off.
<b><u>Solution</u></b>
There is no real solution to this problem. You can make some additional checks to see if the player is still online at a certain moment, and end the script when the person logged off.

------------------------------------------------------------------------

#### npc_timerevent: Attached player not found.

Source Syntax: ShowError("npc_timerevent: Attached player not found.\\n");
<b><u>Cause</u></b>
This error is of the same type as above.
<b><u>Solution</u></b>
There is no real solution to this problem. You can make some additional checks to see if the player is still online at a certain moment, and end the script when the person logged off.

------------------------------------------------------------------------

#### npc_timerevent: NPC not found??

Source Syntax: ShowError("npc_timerevent: NPC not found??\\n");
<b><u>Cause</u></b>
Somehow, some way, between the loading of the NPC and the current timerevent, the NPC went missing. This is possible in a couple of different ways, but the most likely one is disabling the target NPC or unloading it.
<b><u>Solution</u></b>
Making a solution for this will be a bit time intensive. You need to make sure that the timerevent cannot be triggered when the NPC is unloaded or disabled. A way to do this, is to make a global variable with the status of the new NPC, or using getmapxy to find if the NPC is still there.

------------------------------------------------------------------------

#### npc_timerevent_start: Attached player not found!

Source Syntax: ShowError("npc_timerevent_start: Attached player not found!\\n");
<b><u>Cause</u></b>
Your script, or in this specific case, your timer, used to have a player attached to it. The player went missing though. This is most likely because the player logged off.
<b><u>Solution</u></b>
There is no real solution to this problem. You can make some additional checks to see if the player is still online at a certain moment, and end the script when the person logged off.

------------------------------------------------------------------------

#### npc_timerevent_stop: Attached player not found!

Source Syntax: ShowError("npc_timerevent_stop: Attached player not found!\\n");
<b><u>Cause</u></b>
Your script, or in this specific case, your timer, used to have a player attached to it. The player went missing though. This is most likely because the player logged off.
<b><u>Solution</u></b>
There is no real solution to this problem. You can make some additional checks to see if the player is still online at a certain moment, and end the script when the person logged off.

------------------------------------------------------------------------

#### npc_touch_areanpc : some bug

Source Syntax: ShowError("npc_touch_areanpc : some bug \\n");
<b><u>Cause</u></b>
This bug should be impossible to produce. If you want to know the details, dive into the source code, but the short explanation is this:

-   Player triggers OnTouch area.
-   Mapserver iterates through all the NPCs on that map, and searches to which NPC this OnTouch area belongs.
-   With this, it runs a counter from 0 to number of npcs - 1.
-   If it finds one, it jumps out early.
-   If it doesn't find one, i is equal to the amount of npcs - 1.
-   i remains untouched then.
-   When i is equal to the max amount of NPCs on the map (so not npcs - 1, but npcs), it gives this error.

Of course, this is impossible to happen, unless there are no NPCs on the map, but then the OnTouch shouldn't be triggered.
<b><u>Solution</u></b>
Report this bug to the [developers](/developers "wikilink"), because it does not have a solution script-wise. Provide them with as much data as possible/

------------------------------------------------------------------------

#### Out of range spawn coordinates: ... (...,...), map size is (...,...) - ... ... (file ...)

Source Syntax: ShowError("Out of range spawn coordinates: %s (%d,%d), map size is (%d,%d) - %s %s (file %s)\\n", map\[mob.m\].name, x, y, map\[mob.m\].xs-1, map\[mob.m\].ys-1, w1,w3, current_file);
<b><u>Cause</u></b>
You tried to spawn a monster outside of the boundaries of the map. This can either be done by negative coordinates, or coordinates bigger than the maximum of the map.
<b><u>Solution</u></b>
Recheck the actual map size, and make sure the spawn coordinates of your mob does not go beyond that. Also, always keep your spawning coordinates not negative.
<b><u>Example</u></b>
Wrong code:

`monster "prt_fild08",-100,5000,"Poring",1002,5;`

Correct code:

`monster "prt_fild08",0,0,"Poring",1002,5;`

------------------------------------------------------------------------

#### Probably TAB is missing in file '...', line '...': \* ... ... ... ...

Source Syntax: ShowError("Probably TAB is missing in file '%s', line '%i':\\n \* %s %s %s %s\\n",current_file,lines,w1,w2,w3,w4);
<b><u>Cause</u></b>
The mapserver could not detect the type that your script should be. This is most likely happening because you miss a tab before the keyword. Or you are using an invalid keyword.
The following list is a list of all possible keywords:

-   duplicate
-   function
-   mapflag
-   monster
-   script
-   setcell
-   shop
-   warp

<b><u>Solution</u></b>
Make sure you have the tabs in the right place, and that you typed the keyword correctly.

------------------------------------------------------------------------

#### wrong map name : ... ... (file ...)

Source Syntax: ShowError("wrong map name : %s %s (file %s)\\n", w1,w3, current_file);
<b><u>Cause</u></b>
The map where you wanted to spawn your monster on, does not exist.
<b><u>Solution</u></b>
Make sure that you typed the name of the map correctly, and that it is loaded by the mapserver. (Check this by warping to it.)

------------------------------------------------------------------------

#### wrong monsters spawn delays : ... ... (file ...)

Source Syntax: ShowError("wrong monsters spawn delays : %s %s (file %s)\\n", w3, w4, current_file);
<b><u>Cause</u></b>
The spawn delays you entered for your mob are too big. The maximum allowed number for both is: 268435455 (ms).
This is equal to:
\* 3 days,

-   2 hours,
-   33 minutes,
-   55 seconds,
-   and 455 milliseconds.

<b><u>Solution</u></b>
Lower the spawn delay times until they are equal to or less than 268435455.

------------------------------------------------------------------------

#### wrong number of monsters : ... ... (file ...)

Source Syntax: ShowError("wrong number of monsters : %s %s (file %s)\\n", w3, w4, current_file);
<b><u>Cause</u></b>
The amount of monsters you tried to spawn is incorrect. It needs to be bigger than 0 and has a limit of 1000.
<b><u>Solution</u></b>
Change the amount of monsters that you are trying to spawn, to a number equal or lower than 1000 and higher than 0.

------------------------------------------------------------------------

### Errors (script.c)

All errors located in script.c that have the \[Error\] tag are listed in this section.
==== ...: ... broken data ! ==== Source Syntax: ShowError("%s: %s broken data !\\n",mapreg_txt,buf1);
<b><u>Cause</u></b>
One of your global variables is corrupted or broken. This can be caused by a hard drive failure, physical damage to the hard-drive or memory and/or saving global variables while the server crashed suddenly. The server detects this by looking if there is any data after the variable name, before a new line is started. The global variable that is broken, is mentioned after the <b>:</b>. Before the <b>:</b> will tell you exactly where your global variables are being stored.
<b><u>Solution</u></b>
The best solution is to manually fix the broken variable. To do this, make sure that your server is completely offline. Then open the file where the global variables are located. Then search for the specific global variable. When you have found the bugged one, either erase it from the file, or give it a correct value (and if needed, array-index). If it is an important variable, you are advised to look in your most recent backup, and use that value as the new value for the broken variable. When you are done, save the file, exit it, and restart your server to see if the error is fixed.

------------------------------------------------------------------------

#### buildin_callshop: Shop \[...\] not found (or NPC is not shop type)

Source Syntax: ShowError("buildin_callshop: Shop \[%s\] not found (or NPC is not shop type)\\n", shopname);
<b><u>Cause</u></b>
You used the callshop command, to call a shop. However, this shop does not exist, or, it does exist, but isn't of the type Shop.
<b><u>Solution</u></b>
Verify that the shop you want to call is actually a shop, and of course, that it exists. And make sure the shop you are calling obeys the rules of shops that can be called with callshop. (More info regarding this, view the callshop example file: )

------------------------------------------------------------------------

#### buildin_checkweight: Wrong item ID or amount.

Source Syntax: ShowError("buildin_checkweight: Wrong item ID or amount.\\n");
<b><u>Cause</u></b>
You tried to check the weight of an invalid item or a negative amount of items.
<b><u>Solution</u></b>
Verify that the item id is 500 or higher (and of course, that it exists). Also, make sure that you are using a positive amount, and not 0 or a negative amount. When using variables to dynamically use this command, make sure that they obey these limits as well.
<b><u>Example</u></b>
Wrong code:

`set @success, checkweight(400,-10);`

Correct code:

`set @success, checkweight(500,10);`

------------------------------------------------------------------------

#### buildin_getcharid: invalid parameter (...).

Source Syntax:
Current: ShowError("buildin_getcharid: invalid parameter (%d).\\n", num);
Until Rev. 11638: ShowError("buildin_getcharid: invalid .\\n");
Note: The error up until 11638 could not happen since it was inaccessible.
<b><u>Cause</u></b>
You have passed on an invalid parameter to the getcharid function.
<b><u>Solution</u></b>
Getcharid() can handle 4 different arguments, being:

`0 - character id`
`1 - party id`
`2 - guild id`
`3 - account id`

You tried to give it a value smaller than 0 or bigger than 3. Please check which kind of id you tried to request and adjust the number accordingly.
<b><u>Example</u></b>
Wrong code:

`getcharid(-1); // I want the party ID.`
`getcharid(33); // I want the account ID.`

Correct code:

`getcharid(1);`
`getcharid(3);`

------------------------------------------------------------------------

#### buildin_getitem: invalid data type for argument \#1 (...).

Source Syntax: ShowError("buildin_getitem: invalid data type for argument \#1 (%d).", data-&gt;type);
<b><u>Cause</u></b>
While using the getitem command, you somehow managed to provide as the first argument, something different than a string or an integer. This command only accepts item names or item ids as a first argument.
<b><u>Solution</u></b>
Make sure that you have entered a valid number or string as the first argument of getitem. When using a variable, of course, make sure that they also obey this.
<b><u>Example</u></b>
Wrong code:

`getitem "@item_name$",4;`
`getitem ^1234, 4;`

Correct code:

`getitem @item_name$, 4;`
`getitem 1234, 4;`

------------------------------------------------------------------------

#### buildin_getitem: Nonexistant item ... requested.

Source Syntax:
ShowError("buildin_getitem: Nonexistant item %s requested.\\n", name);
ShowError("buildin_getitem: Nonexistant item %d requested.\\n", nameid);
<b><u>Cause</u></b>
The item that you wanted to give with getitem does not exist.
<b><u>Solution</u></b>
Make sure that the name or the item id which you provided is an actual item. Of course, when using variables to give the item, make sure that they obey this as well.
<b><u>Example</u></b>
Wrong code:

`getitem 400,5;`
`getitem "Appel",5;`

Correct code:

`getitem 500,5;`
`getitem "Apple",5;`

------------------------------------------------------------------------

#### buildin_getmonsterinfo: Wrong Monster ID: ...

Source Syntax: ShowError("buildin_getmonsterinfo: Wrong Monster ID: %i\\n", mob_id);
<b><u>Cause</u></b>
The monster ID of the monster you wanted to get information on, does not exist.
<b><u>Solution</u></b>
Make sure the mob_id is the mob_id of an existing monster in one of your mob_db files.
<b><u>Example</u></b>
Wrong code:

`getmonsterinfo(800,MOB_NAME);`

Correct code:

`getmonsterinfo(1002,MOB_NAME);`

------------------------------------------------------------------------

#### buildin_getnpctimer: Attached player not found!

Source Syntax: ShowError("buildin_getnpctimer: Attached player not found!\\n");
<b><u>Cause</u></b>
You have attached a player to your NPCTimer. When you tried using getnpctimer on that specific timer, the player was not found anymore. This often means that he is offline.
<b><u>Solution</u></b>
First ask yourself, if it is really needed to attach a player to your NPCTimer. If this is the case, and you do not want to get this error, then you might want to consider using addtimer (a player timer) instead. If you truely want to use NPCTimers with a player attached, then before using getnpctimer, do a check if the player is still online.

------------------------------------------------------------------------

#### buildin_rid2name: BL type unknown.

Source Syntax: ShowError("buildin_rid2name: BL type unknown.\\n");
<b><u>Cause</u></b>
In some incredible way, you managed to provide the RID of a group that does not exist. This command can be used on the RID of the following groups only:

-   Homunculus
-   Monster
-   NPC
-   Pet
-   Player

There are some other things which have RIDs, like floor items, skill traps etc. These are not allowed with this function.
<b><u>Solution</u></b>
The most likely cause for this bug is that you have provided an invalid RID, which accidentally does have a so called BL-status. (BL means BlockList, in which essential data is stored. Too complicated to explain it in here in a few words.) Make sure you are using a valid RID for this function.

------------------------------------------------------------------------

#### buildin_rid2name: invalid RID

Source Syntax: ShowError("buildin_rid2name: invalid RID\\n");
<b><u>Cause</u></b>
You managed to provide an invalid RID. This means, that the RID you gave to the rid2name command, does not exist and does not have a BL attached to it. Most probable is that you provided 0 as the RID, which never exists, or the RID of something that used to be, but isn't anymore. (For example, a player who logged off, or a monster which got killed.)
<b><u>Solution</u></b>
Recheck if you are providing a correct RID. If this is the case, check if it can be sensitive for certain events, like player logging off or monster being killed. If this is the case, then put some additional checks in place to prevent this bug for happening. In the case of player logging off, do a check with the isloggedin command. In the case of a monster, check if it is still alive, etc. etc.

------------------------------------------------------------------------

#### buildin_soundeffectall: insufficient arguments for specific area broadcast.

Source Syntax: ShowError("buildin_soundeffectall: insufficient arguments for specific area broadcast.\\n");
<b><u>Cause</u></b>
You didn't provide enough arguments for soundeffectall. Soundeffectall can be used in two ways. One way is with a predefined coverage (bc_all, bc_map etc. constants), which all have a numerical value lower than 23, even when added to each other. The other way, is providing a coverage equal to or bigger than 23, which allows you to define a custom area on a custom map, where the sound will be played.
In this case, you provided a coverage which had a numerical value of 23 or higher, you will have to provide a mapname, and an area by giving x0, y0, x1 and y1. Unfortunately, you failed to do exactly that.
<b><u>Solution</u></b>
If it was your intend to use a custom area, then make sure you provided all of the 8 arguments. For the custom area, this is the format:

`soundeffectall "effect filename",`<number>`,`<coverage>`,"mapname",`<x0>`,`<y0>`,`<x1>`,`<y2>`;`

where coverage &gt;= 23. If you intended to use a predefined area, make sure that the numerical value of coverage is smaller than 23. To check this, open up db/const.txt, and look up the values behind the bc_ entries. Add up the numbers of the bc's that you used, to see if it stays under 23.

------------------------------------------------------------------------

#### buildin_warp: moving player '...' to "...",...,... failed.

Source Syntax: ShowError("buildin_warp: moving player '%s' to \\"%s\\",%d,%d failed.\\n", sd-&gt;status.name, str, x, y);
<b><u>Cause</u></b>
The server wasn't able to warp the specific target to its new location. There are two possible reasons for this to happen.

`1 - Invalid map index.`
`2 - Map not in this map-server, and failed to locate alternate map-server.`

<b><u>Solution</u></b>
Make sure you supplied the correct mapname to the warp function and make sure that the map is loaded and enabled in the mapserver.

------------------------------------------------------------------------

#### can't read ...

Source Syntax: ShowError("can't read %s\\n", line);
<b><u>Cause</u></b>
Your mapserver failed to open up the file located at: "db/const.txt".
<b><u>Solution</u></b>
This can be caused by a couple of things. Either the file isn't located there anymore (it was renamed, moved or deleted), or the file is already opened by some other application which locked it from reading. Make sure that the file exists and isn't in use by any other application, not even a text editor.

------------------------------------------------------------------------

#### Failed to save the mapreg data!

Source Syntax: ShowError("Failed to save the mapreg data!\\n");
<b><u>Cause</u></b>
This error is not related to bugs in the actual code of a script. It is part of the auto-save routine where the global variables are written to permanent storage (save/mapreg.txt for TXT and SQL, or the mapreg table for SQL if you defined the DMAPREGSQL flag when you compiled your source code). This error does not occur when you compiled your code in such a way that it saves your global variables to the SQL table named mapreg. However, in any other case, at certain intervals, your mapserver auto-saves the global variables to the file in save/mapreg.txt. When it occurs a problem during this, being unable to open or write to the file, then the mapserver will not save the global variables, and will return this error.
<b><u>Solution</u></b>
A long story short: You will have to verify that the file save/mapreg.txt is not locked from writing. Reasons for the file to be locked, is when it is opened by another application, like a text editor, or when the last time it was used, it wasn't closed properly. So, make sure that it is not locked anymore. (Do not close the mapserver in the meantime, or all your global variables might get lost.)

------------------------------------------------------------------------

#### file not found: \[...\]

Source Syntax: ShowError("file not found: \[%s\]\\n", cfgName);
<b><u>Cause</u></b>
This error occurs when your mapserver is unable to find or open conf/script_athena.conf.
<b><u>Solution</u></b>
Make sure that the file is not locked and does exist. To check if it is locked, check if it is in use by any other program, like a text-editor. If any other application has the file opened, close that application.

------------------------------------------------------------------------

#### function not found

Source Syntax: ShowError("function not found\\n");
<b><u>Cause</u></b>
This usually happens, when you have declared a function name, but did not implement the function.
<b><u>Solution</u></b>
Add code for every declared function.
<b><u>Example</u></b>
Wrong code:

`function NonExistingFunction;`
`// ...`
`NonExistingFunction;`

Correct code:

`function ExistingFunction;`
`// ...`
`ExistingFunction;`
`// ...`
`function ExistingFunction {`
`    // code`
`}`

------------------------------------------------------------------------

#### getnpctimer: Invalid NPC

Source Syntax: ShowError("getnpctimer: Invalid NPC\\n");
<b><u>Cause</u></b>
You tried accessing a NPC timer of a NPC that does not exist.
<b><u>Solution</u></b>
Recheck if the NPC that you want to look up the NPC timer of, actually exists, and that you did not make any typos in the name.

------------------------------------------------------------------------

#### initnpctimer: invalid argument type \#1 (needs be int or string)).

Source Syntax: ShowError("initnpctimer: invalid argument type \#1 (needs be int or string)).\\n");
<b><u>Cause</u></b>
You tried using initnpctimer, and gave an invalid argument. This command can be used in conjunction with a string (NPC name) or an integer (starting value).
<b><u>Solution</u></b>
Recheck if you actually needed an argument to use this command, and when this is the case, if it is actually a correct argument.
<b><u>Example</u></b>
Wrong code:

`initnpctimer "@NPC_Name$";`

Correct code:

`initnpctimer @NPC_Name$;`

------------------------------------------------------------------------

#### NPC event parameter deprecated! Please use 'NPCNAME::OnEVENT' instead of '...'.

Source Syntax: ShowError("NPC event parameter deprecated! Please use 'NPCNAME::OnEVENT' instead of '%s'.\\n",evt);
<b><u>Cause</u></b>
In the past, when you wanted to specify a NPC event, you could simply use OnEvent. This has changed a while back though. Now you must use the format NPCNAME::OnEvent. You most likely forgot to either include the NPC name, or the On part of the event label.
<b><u>Solution</u></b>
Check if you obey the format, and that your event label really starts with On.

------------------------------------------------------------------------

#### run_func : ...? (...(...))

Source Syntax: ShowError("run_func : %s? (%d(%d))\\n",str_buf+str_data\[func\].str,func,str_data\[func\].type);
<b><u>Cause</u></b>
This is an error that occurs deep inside the code, and is therefor probably rare to encounter. It basically means, that the function that the server is trying to run, is actually not a function. A possible scenario where this can occur, is a default start up, and while the server is up, you do an @loadnpc <npc>. However, this new NPC has a variable named exactly like a function, and now overwrites it.
<b><u>Solution</u></b>
Check in your scripts if the function really is a function, and if no other NPC overwrites the function, by using the same name as a variable name or something likewise.

------------------------------------------------------------------------

#### run_func: '...' (type ...) is not function and command!

Source Syntax: ShowError("run_func: '"CL_WHITE"%s"CL_RESET"' (type %d) is not function and command!\\n", str_buf+str_data\[func\].str, str_data\[func\].type);
<b><u>Cause</u></b>
This is an error that occurs deep inside the code, and is therefor probably rare to encounter. It basically means, that the function that the server is trying to run, is actually not a function. A possible scenario where this can occur, is a default start up, and while the server is up, you do an @loadnpc <npc>. However, this new NPC has a variable named exactly like a function, and now overwrites it.
<b><u>Solution</u></b>
Check in your scripts if the function really is a function, and if no other NPC overwrites the function, by using the same name as a variable name or something likewise.

------------------------------------------------------------------------

#### run_script: infinity loop !

Source Syntax: ShowError("run_script: infinity loop !\\n");
<b><u>Cause</u></b>
You managed to create a loop in your script, which is never ending. Because this may result into a lock up of your server, because of high CPU usage, the mapserver gives you this error.
<b><u>Solution</u></b>
Check if the infinite loop really needs to exist, and if not, make sure that there is an exit possibility.
<b><u>Example</u></b>
Wrong code:

`while(1) {`
`   set @i, @i + 1;`
`   mes @i;`
`   next;`
`}`

Correct code:

`while(@i < 100) {`
`   set @i, @i + 1;`
`   mes @i;`
`   next;`
`}`

------------------------------------------------------------------------

#### script: jump_zero: not label !

Source Syntax: ShowError("script: jump_zero: not label !\\n");
<b><u>Cause</u></b>
The label you provided with the jump_zero command, isn't a label.
<b><u>Solution</u></b>
Recheck if the label exists, and uses the correct formatting of label names.
<b><u>Example</u></b>
Wrong code:

`jumpzero(Zeny), 1337;`

Correct code:

`jumpzero(Zeny), L_IsBroke;`

------------------------------------------------------------------------

#### script:callfunc: function not found! \[...\]

Source Syntax: ShowError("script:callfunc: function not found! \[%s\]\\n",str);
<b><u>Cause</u></b>
You tried to call a function with callfunc, which does not exist.
<b><u>Solution</u></b>
Recheck if you did not make any typos in the make of the function, and that the function really exists.

------------------------------------------------------------------------

#### script:callsub: argument is not a label

Source Syntax:
Current: ShowError("script:callsub: argument is not a label\\n");
Until Rev. 10812: ShowError("script: callsub: not label !\\n");
<b><u>Cause</u></b>
The label you provided for your callsub does not exist.
<b><u>Solution</u></b>
Recheck if you did not make any typos in the subroutine which you are trying to call. Make sure the label exists.

------------------------------------------------------------------------

#### script:cleararray: illegal scope

Source Syntax: ShowError("script:cleararray: illegal scope\\n");
<b><u>Cause</u></b>
This error indicates that you tried to use cleararray on a variable which isn't an array.
<b><u>Solution</u></b>
Recheck if the array you want to clear actually is an array, and that you typed the name of the array correctly.

------------------------------------------------------------------------

#### script:cleararray: not a variable

Source Syntax: ShowError("script:cleararray: not a variable\\n");
<b><u>Cause</u></b>
The variable you tried to clear with cleararray, isn't a variable, or it isn't a legal variable name.
<b><u>Solution</u></b>
Confirm that the variable does exist, and that it obeys the official rules for names of a variable. For reference, check this link: [Variables\#Other_Important_Info Naming Variables](/Variables#Other_Important_Info_Naming_Variables "wikilink")
<b><u>Example</u></b>
Wrong code:

`cleararray .1st_array[0],0,5;`

Correct code:

`cleararray .First_array[0],0,5;`

------------------------------------------------------------------------

#### script:conv_num: cannot convert to number, defaulting to 0

Source Syntax: ShowError("script:conv_num: cannot convert to number, defaulting to 0\\n");
<b><u>Cause</u></b>
You tried converting something which isn't a string nor a valid number, to a decimal integer. The mapserver replaced what you tried to convert, to 0. The mapserver is capable of automatically converting strings, octal numbers ("o377") and hex numbers ("0xFF").
<b><u>Solution</u></b>
Check if all your (unmeant/silent) conversions are alright, and if you did not try to convert for example a binary number ("0b10011101") to a decimal integer.
<b><u>Example</u></b>
Wrong code:

`set @i, 0b10011101; // 0b10011101 equals to 157 as decimal number, 0x9D as hex, or o235 as octonal.`

Possible correct codes:

`set @i, 0x9D; `
`set @i, o235;`
`set @i, 157;`

------------------------------------------------------------------------

#### script:conv_num: overflow detected, capping to ...

Source Syntax: ShowError("script:conv_num: overflow detected, capping to %ld\\n", num);
<b><u>Cause</u></b>
This error occurs when you try to convert a number from a different system than decimal, and the result is bigger than what an integer can hold. This maximum is 2,147,483,647. When this happens, to prevent memory corruption or buffer overflow, the mapserver automatically caps the number at this maximum.
<b><u>Solution</u></b>
Calculate if the number which you try to convert to the decimal system, is less than the maximum allowed. Change when needed, to prevent unexpected results.
<b><u>Example</u></b>
Wrong code:

`set @result, 0xFFFF * 0xFFFF; // 65535 * 65535 = 4294836225.`
`mes "0xFFFF * 0xFFFF = "+@result; // Displays: "0xFFFF * 0xFFFF = 2147483647"`

Correct code:

`set @i1, 0xFFFF; // Converts to 65535`
`set @i2, 0xFFFF; // Converts to 65535`
`set @temp_low, @i1 * (@i2%1000); // 65535 * (65535%1000) = 65535 * 535 = 35061225 (Fits.)`
`set @temp_high, @i1 * (@i2/1000); // 65535 * (65535/1000) = 65535 * 65 = 4259775 (Fits.)`
`set @result_low, @temp_low%1000; // We only need the lower part: 35061225%1000 = 225`
`set @result_high, @temp_high + (@temp_low/1000); // 4259775 + (35061225/1000) = 4259775 + 35061 = 4294836`
`mes "0xFFFF * 0xFFFF = "+@result_high+@result_low; // Displays: "0xFFFF * 0xFFFF = 4294836225"`

Short Correct code:

`set @result_low, (0xFFFF * (0xFFFF%1000))%1000;`
`set @result_high, (0xFFFF * (0xFFFF/1000)) + ((0xFFFF * (0xFFFF%1000))%1000)/1000;`
`mes "0xFFFF * 0xFFFF = "+@result_high+@result_low; // Displays: "0xFFFF * 0xFFFF = 4294836225"`

Short Compact Correct code:

`set @result_low, (0xFFFF * (0xFFFF%1000))%1000;`
`set @result_high, (0xFFFF * 0xFFFF + (0xFFFF%1000) * (0xFFFF%1000))/1000;`
`mes "0xFFFF * 0xFFFF = "+@result_high+@result_low; // Displays: "0xFFFF * 0xFFFF = 4294836225"`

------------------------------------------------------------------------

#### script:conv_num: underflow detected, capping to ...

Source Syntax: ShowError("script:conv_num: underflow detected, capping to %ld\\n", num);
<b><u>Cause</u></b>
This error is telling you the opposite of the previous error. Due to converting numbers or calculations, your result has become lower than the lowest possible integer which your mapserver can store. As a safety precaution, it has set the value to -2,147,483,648
<b><u>Solution</u></b>
Calculate if the number which you try to convert to the decimal system, is more than the minimum allowed. Change when needed, to prevent unexpected results.

------------------------------------------------------------------------

#### script:conv_str: cannot convert to string, defaulting to ""

Source Syntax: ShowError("script:conv_str: cannot convert to string, defaulting to \\"\\"\\n");
<b><u>Cause</u></b>
You tried converting something to a string, but the mapserver was unable to convert this. Therefor, it has used the empty string "" instead.
<b><u>Solution</u></b>
Make sure you entered something that can be converted to a string. Things need to be converted when for example displaying a number in a mes-dialogue.
<b><u>Example</u></b>
Wrong code:

`mes "You are the "+ 1st +"."; // 1st is not a valid string, nor a valid number.`

Correct code:

`mes "You are the first.";`
`mes "You are the "+1+"st.";`

------------------------------------------------------------------------

#### script:copyarray: illegal scope

Source Syntax: ShowError("script:copyarray: illegal scope\\n");
<b><u>Cause</u></b>
This error indicates that you tried to use copyarray on a variable which isn't an array.
<b><u>Solution</u></b>
Recheck if the array you want to copy actually is an array, and that you typed the name of the array correctly. Of course, also check this for the target array.

------------------------------------------------------------------------

#### script:copyarray: not a variable

Source Syntax: ShowError("script:copyarray: not a variable\\n");
<b><u>Cause</u></b>
The variable you tried to copy with copyarray, isn't a variable, or it isn't a legal variable name.
<b><u>Solution</u></b>
Confirm that the variable does exist, and that it obeys the official rules for names of a variable. For reference, check this link: [Variables\#Other_Important_Info Naming Variables](/Variables#Other_Important_Info_Naming_Variables "wikilink")
<b><u>Example</u></b>
Wrong code:

`copyarray @2ndarray2[0],@1starray[2],2;`

Correct code:

`copyarray @secondarray2[0],@firstarray[2],2;`

------------------------------------------------------------------------

#### script:copyarray: type mismatch

Source Syntax: ShowError("script:copyarray: type mismatch\\n");
<b><u>Cause</u></b>
You tried copying an integer array to a string array, or the other way around.
<b><u>Solution</u></b>
Make sure that both either have the $-suffix, or do not have the string suffix.
<b><u>Example</u></b>
Wrong code:

`copyarray @MyArray2$[0],@MyArray1[2],2;`

Correct code:

`copyarray @MyArray2[0],@MyArray1[2],2; `

------------------------------------------------------------------------

#### script:deletearray: illegal scope

Source Syntax: ShowError("script:deletearray: illegal scope\\n");
<b><u>Cause</u></b>
This error indicates that you tried to use deletearray on a variable which isn't an array.
<b><u>Solution</u></b>
Recheck if the array you want to delete actually is an array, and that you typed the name of the array correctly.

------------------------------------------------------------------------

#### script:deletearray: not a variable

<b><u>Cause</u></b>
The variable you tried to delete with deletearray, isn't a variable, or it isn't a legal variable name.
<b><u>Solution</u></b>
Confirm that the variable does exist, and that it obeys the official rules for names of a variable. For reference, check this link: [Variables\#Other_Important_Info Naming Variables](/Variables#Other_Important_Info_Naming_Variables "wikilink")
<b><u>Example</u></b>
Wrong code:

`deletearray .1st_array[0],5;`

Correct code:

`deletearray .First_array[0],5;`

------------------------------------------------------------------------

==== script:getarg: index (idx=...) out of range (count=...) and no default value found ==== Source Syntax: ShowError("script:getarg: index (idx=%d) out of range (count=%d) and no default value found\\n", idx, count);
<b><u>Cause</u></b>
You tried to use getarg() on a non-existing parameter. When calling a function or a subroutine, you can give certain parameters to it. These parameters can be requested with getarg(). Getarg can be used in combination with optional parameters though. For this, you will have to specify a default value. Here is how to do that:

`set @temp, getarg(0); //Normal getarg. Will give the error if it does not exist.`
`set @temp, getarg(5,10); // Special getarg. If getarg(5) does not exist, it will use the value 10, and will not give this error.`

<b><u>Solution</u></b>
Check if the parameter you want to obtain with getarg, always exists. (Keep in mind, getarg starts with 0, not with 1.) If it should always exist, check your callfunc and callsub lines and anything related to it. However, if the parameter is optional, then use the second format, where you can provide a default value when the parameter has not been given.
<b><u>Example</u></b>
Wrong code:

`callfunc "F_MyFunction",5,10;`
`...`
`F_MyFunction:`
`  set @MF_start, getarg(0);`
`  set @MF_end, getarg(1);`
`  set @MF_increase, getarg(2);`

Correct code:

`callfunc "F_MyFunction",5,10;`
`...`
`F_MyFunction:`
`  set @MF_start, getarg(0);`
`  set @MF_end, getarg(1);`
`  set @MF_increase, getarg(2,1);`

------------------------------------------------------------------------

#### script:getarg: no callfunc or callsub!

Source Syntax: ShowError("script:getarg: no callfunc or callsub!\\n");
<b><u>Cause</u></b>
You tried using getarg without having called the function or subroutine. In layman's terms, this means: You used goto F_MyFunction;, instead of callfunc "F_MyFunction"; Or, you used getarg in a piece of normal code, and not in a subroutine or a function.
<b><u>Solution</u></b>
First check if the getarg command is inside a real function or subroutine. If this isn't the case, remove it or make the piece of code a real function or subroutine. If the getarg is inside a real function or subroutine, and you are still getting the error, then this means that you have jumped to the function or subroutine in a weird way. Check if you used anything like goto <function or subname>; or if the code in advance of the function/sub isn't properly ended. This last thing can happen when you have some code above the sub or function, which doesn't have a close; or end; at the end.

------------------------------------------------------------------------

#### script:getarraysize: illegal scope

Source Syntax: ShowError("script:getarraysize: illegal scope\\n");
<b><u>Cause</u></b>
This error indicates that you tried to use getarraysize on a variable which isn't an array.
<b><u>Solution</u></b>
Recheck if the array you want to get the size of, actually is an array, and that you typed the name of the array correctly.

------------------------------------------------------------------------

#### script:getarraysize: not a variable

Source Syntax: ShowError("script:getarraysize: not a variable\\n");
<b><u>Cause</u></b>
The variable you tried to obtain the size of with getarraysize, isn't a variable, or it isn't a legal variable name.
<b><u>Solution</u></b>
Confirm that the variable does exist, and that it obeys the official rules for names of a variable. For reference, check this link: [Variables\#Other_Important_Info Naming Variables](/Variables#Other_Important_Info_Naming_Variables "wikilink")
<b><u>Example</u></b>
Wrong code:

`set @temp, getarraysize(.1st_array);`

Correct code:

`set @temp, getarraysize(.First_array);`

------------------------------------------------------------------------

#### script:getelementofarray: illegal scope

Source Syntax: ShowError("script:getelementofarray: illegal scope\\n");
<b><u>Cause</u></b>
This error indicates that you tried to use getelementofarray on a variable which isn't an array.
<b><u>Solution</u></b>
Recheck if the array you want to get an element of, actually is an array, and that you typed the name of the array correctly.

------------------------------------------------------------------------

#### script:getelementofarray: not a variable

Source Syntax: ShowError("script:getelementofarray: not a variable\\n");
<b><u>Cause</u></b>
The variable you tried to get an element of with getelementofarray, isn't a variable, or it isn't a legal variable name.
<b><u>Solution</u></b>
Confirm that the variable does exist, and that it obeys the official rules for names of a variable. For reference, check this link: [Variables\#Other_Important_Info Naming Variables](/Variables#Other_Important_Info_Naming_Variables "wikilink")
<b><u>Example</u></b>
Wrong code:

`set @temp, getelementofarray(.1st_array,5);`

Correct code:

`set @temp, getelementofarray(.First_array,5);`

------------------------------------------------------------------------

#### script:getvariableofnpc: can't find npc ...

Source Syntax:
Current: ShowError("script:getvariableofnpc: can't find npc %s\\n", script_getstr(st,3));
Until Rev. 10812: ShowError("script: getvariableofnpc: can't find npc %s\\n", npcname);
<b><u>Cause</u></b>
You tried to request the variable of a NPC which doesn't exist.
<b><u>Solution</u></b>
Check if the NPC you want to get the variable of, indeed exists. Of course, also check if you did not make any typos in the name of the NPC.

------------------------------------------------------------------------

#### script:getvariableofnpc: invalid scope (not npc variable)

Source Syntax:
Current: ShowError("script:getvariableofnpc: invalid scope (not npc variable)\\n");
Until Rev. 10812: ShowError("script: getvariableofnpc: invalid scope %s (not npc variable)\\n", var_name);
<b><u>Cause</u></b>
You tried requesting the value of a variable, which isn't a permanent npc variable. (Meaning, only has the prefix '.' and no @.) This command can only be used to access permanent npc variables.
<b><u>Solution</u></b>
Check if the variable you are trying to request is an actual permanent npc variable. If this is not the cause of the error, then you will have to change the other NPC and make the variable in there a permanent NPC varable. Adjust the variable name of the line getvariableofnpc accordingly of course.

------------------------------------------------------------------------

#### script:getvariableofnpc: not a variable

Source Syntax:
Current: ShowError("script:getvariableofnpc: not a variable\\n");
Until Rev. 10812: ShowError("script: getvariableofnpc: first argument is not a variable name\\n");
<b><u>Cause</u></b>
The variable you requested does not obey the rules of variable naming. That, or the slight possibility that it doesn't exist.
<b><u>Solution</u></b>
Check if you wrote the name correctly and if it obeys the rules of variable naming. For reference, check this link: [Variables\#Other_Important_Info Naming Variables](/Variables#Other_Important_Info_Naming_Variables "wikilink")
Also check if you did not make the same mistake in the NPC where you want to get the variable of.
<b><u>Example</u></b>
Wrong code:

`set @temp, getvariableofnpc(.1stVar,"MyFirstNPC");`

Correct code:

`set @temp, getvariableofnpc(.FirstVar,"MyFirstNPC");`

------------------------------------------------------------------------

#### script:goto: not a label

Source Syntax:
Current: ShowError("script:goto: not a label\\n");
Until Rev. 10812: ShowError("script:goto: not label!\\n");
<b><u>Cause</u></b>
You tried to jump to a label which doesn't exist, or isn't defined as a label.
<b><u>Solution</u></b>
Check the name, to see if it is correct. Also check if the label exists. If this both is the case, and you still get the error, then make sure that the name is different from any variable name, function name, subroutine name and command name.

------------------------------------------------------------------------

#### script:guardian: invalid data type for argument \#6 (from 1)

Source Syntax:
Current: ShowError("script:guardian: invalid data type for argument \#6 (from 1)\\n");
Until Rev. 10812: ShowError("buildin_guardian: invalid data type for argument \#8 (%d).", data-&gt;type);
<b><u>Cause</u></b>
Your sixth argument for the guardian command isn't of the correct type. You will have to use one of the following formats:

`guardian "`<map name>`",`<x>`,`<y>`,"`<name to show>`",`<mob id>`;`
`guardian "`<map name>`",`<x>`,`<y>`,"`<name to show>`",`<mob id>`,"`<event label>`";`
`guardian "`<map name>`",`<x>`,`<y>`,"`<name to show>`",`<mob id>`,`<guardian index>`;`
`guardian "`<map name>`",`<x>`,`<y>`,"`<name to show>`",`<mob id>`,"`<event label>`",`<guardian index>`;`

In essence, this means, that your event label and/or guardian index is not respectively a string and/or an integer. (The index needs to be an integer, the event label needs to be a string.)
<b><u>Solution</u></b>
Check if you are using the correct type for the specific argument you want to use. Make sure that the sixth argument really is a string or an integer.

------------------------------------------------------------------------

#### script:input: not a variable

Source Syntax:
Current: ShowError("script:input: not a variable\\n");
Until Rev. 10812: ShowError("script: buildin_input: given argument is not a variable!\\n");
<b><u>Cause</u></b>
You tried to use input on a variable which isn't a variable. This means that you are naming your variable wrong, or that you typed the name of a command, label, function or subroutine.
<b><u>Solution</u></b>
Verify that you are obeying the rules for variable naming, and that the name you use isn't already taken by any command, label, function or subroutine.

------------------------------------------------------------------------

#### script:menu: argument \#... (from 1) is not a label or label not found.

Source Syntax:
Current: ShowError("script:menu: argument \#%d (from 1) is not a label or label not found.\\n", i);
Until Rev. 10812: ShowError("script:menu: argument \#%d (from 1) is not a label or label not found (op=%s).\\n", i, script_op2name(data-&gt;type));
<b><u>Cause</u></b>
The target label you provided for a specific menu option, is not a correct label name, or does not exist. Please note that in a menu, the dash (-) is a valid replacement for a label.
<b><u>Solution</u></b>
Verify that the reported label does exist, and is correctly typed, and that it also obeys the rules for label naming.

------------------------------------------------------------------------

#### script:menu: illegal number of arguments (...).

Source Syntax: ShowError("script:menu: illegal number of arguments (%d).\\n", (script_lastdata(st) - 1));
<b><u>Cause</u></b>
The amount of arguments in your menu is not even. This makes it an invalid menu, because every menu option needs to be accompanied by a label where it should go to.
<b><u>Solution</u></b>
Check if you have put your commas between every menu option and label, and check if every menu option is accompanied by a label.
<b><u>Example</u></b>
Wrong code:

`menu "Option 1",Label_1,"Option 2";`

Correct code:

`menu "Option 1",Label_1,"Option 2",Label_2; `

or

`menu "Option 1",Label_1,"Option 2",-;`

------------------------------------------------------------------------

#### script:menu: unexpected data in label argument

Source Syntax: ShowError("script:menu: unexpected data in label argument\\n");
<b><u>Cause</u></b>
The target label you provided for a specific menu option, is not a correct label name, or does not exist. Please note that in a menu, the dash (-) is a valid replacement for a label.
<b><u>Solution</u></b>
Verify that the reported label does exist, and is correctly typed, and that it also obeys the rules for label naming.

------------------------------------------------------------------------

==== script:op_1: argument is not a number (op=...) ==== Source Syntax:
Current: ShowError("script:op_1: argument is not a number (op=%s)\\n", script_op2name(op));
Until Rev. 10812: ShowError("script:op_1: invalid type of data op:%s [data:%s\\n](data:%s\n)", script_op2name(op), script_op2name(data-&gt;type));
<b><u>Cause</u></b>
You tried to use an arithmetic operation (mathematical operation) that uses a single value, on something else than an integer.
<b><u>Solution</u></b>
Make sure that what you provided as argument is indeed an integer.
<b><u>Example</u></b>
Wrong code:

`if(!"Hello") close;`

Correct code:

`if(!(MyInput$ == "Hello")) close;`

or

`if(!MyVariable) close;`

------------------------------------------------------------------------

==== script:op_1: unexpected operator ... i1=... ==== Source Syntax:
Current: ShowError("script:op_1: unexpected operator %s i1=%d\\n", script_op2name(op), i1);
Until Rev. 10812: ShowError("script:op_1: unexpected operator op:%s\\n", script_op2name(op));
<b><u>Cause</u></b>
You tried using a single variable mathematical operator which isn't valid. For the recap, these are the possible arithmetic operators that only use a single variable:

`set var, -var; // Make negative. (dash)`
`set var, !var; // Integer inversion. (exclamation mark)`
`set var, ~var; // Bitwise inversion. (tilde)`

<b><u>Solution</u></b>
Make sure that you have provided the right sign for this single argument operator.

------------------------------------------------------------------------

#### script:op_2: invalid data for operator ...

Source Syntax:
Current: ShowError("script:op_2: invalid data for operator %s\\n", script_op2name(op));
Until Rev. 10812: ShowError("script:op_2: invalid type of data op:%s left:%s right:%s\\n", script_op2name(op), script_op2name(left-&gt;type), script_op2name(right-&gt;type));
<b><u>Cause</u></b>
You provided either an invalid type of argument (not string and not integer), or you used an operator which isn't ADD, and tried to use it on a string in combination with an integer.
<b><u>Solution</u></b>
If you are using ADD (+), then make sure that you did provide either strings, integers or both, and not an invalid type of data. In any other case, make sure that you provided two strings or two integers.

------------------------------------------------------------------------

==== script:op_2num: division by zero detected op=... i1=... i2=... ==== Source Syntax:
Current: ShowError("script:op_2num: division by zero detected op=%s i1=%d i2=%d\\n", script_op2name(op), i1, i2);
Until Rev. 10812: ShowError("script:op_2num: division by zero detected op:%s\\n", script_op2name(op));
<b><u>Cause</u></b>
You used the operator MOD (%) or DIV (/) where you divided the given number by 0. This is impossible to calculate, since any division by 0 is undefined, even in the real world math.
<b><u>Solution</u></b>
Change the formula in such a way, that it isn't dividing by zero. When using a variable divide-by-number, make sure that this variable can never be 0.
<b><u>Example</u></b>
Wrong code:

`set @result, my_var%0;`
`set @result, my_var/0;`

Correct code:

`set @result, my_var%5;`
`set @result, my_var/2;`

------------------------------------------------------------------------

==== script:op_2num: unexpected number operator ... i1=... i2=... ==== Source Syntax:
Current: ShowError("script:op_2num: unexpected number operator %s i1=%d i2=%d\\n", script_op2name(op), i1, i2);
Until Rev. 10812: ShowError("script:op_2num: unexpected number operator op:%s\\n", script_op2name(op));
<b><u>Cause</u></b>
You tried using an operator which isn't supported by the Athena Scripting Engine. The following operators for calculations with 2 integers are allowed:

-   a & b // Bitwise AND (C_AND)
-   a | b // Bitwise OR (C_OR)
-   a ^ b // Bitwise XOR (Exclusive OR or C_XOR)
-   a && b // Logical AND (C_LAND)
-   a || b // Logical OR (C_LOR)
-   a == b // Is equal to (C_EQ)
-   a != b // Is unqual to (C_NE)
-   a &gt; b // Is greater than (C_GT)
-   a &gt;= b // Is greater than or equal to (C_GE)
-   a &lt; b // Is smaller than (C_LT)
-   a &lt;= b // Is smaller than or equal to (C_LE)
-   a &gt;&gt; b // Bitshift right (C_R_SHIFT)
-   a &lt;&lt; b // Bitshift left (C_L_SHIFT)
-   a / b // Division (C_DIV)
-   a % b // Modulus (C_MOD)
-   a + b // Addition (C_ADD)
-   a - b // Substraction (C_SUB)
-   a \* b // Multiplication (C_MUL)

<b><u>Solution</u></b>
Check which operator of the ones above you wanted to use, and make sure you use that one.

------------------------------------------------------------------------

#### script:op2_str: unexpected string operator ...

Source Syntax:
Current: ShowError("script:op2_str: unexpected string operator %s\\n", script_op2name(op));
Until Rev. 10812: ShowError("script:op2_str: unexpected string operator op:%s\\n", script_op2name(op));
<b><u>Cause</u></b>
You tried using a string operator on two strings, which doesn't exist. The following Binary String Operators are allowed:

-   a$ == b$ // Is equal to (C_EQ)
-   a$ != b$ // Is not equal to (C_NE)
-   a$ &gt; b$ // Is greater than (C_GT)
-   a$ &gt;= b$ // Is greater than or equal to (C_GE)
-   a$ &lt; b$ // Is smaller than (C_LT)
-   a$ &lt;= b$ // Is smaller than or equal to (C_LE)
-   a$ + b$ // Combine strings (C_ADD)

Please note: Binary in Binary String Operators does not mean bitwise, it simply means it uses two arguments. Also note: Only the ADD operator returns a string. The other operators return an integer. Third note, the operators with smaller than and bigger than in it, well, that isn't the actual way it works. You will have to dive into a manual on strcmp to read what it does exactly.
<b><u>Solution</u></b>
Check which operator of the ones above you wanted to use, and make sure you use that one.

------------------------------------------------------------------------

#### script:op_3: invalid data for the ternary operator test

Source Syntax:
Current: ShowError("script:op_3: invalid data for the ternary operator test\\n");
Until Rev. 10812: ShowError("script:op_3: invalid type of data op:%s [data:%s\\n](data:%s\n)", script_op2name(op), script_op2name(data-&gt;type));
<b><u>Cause</u></b>
There is one single Ternary Operator which you can use in the Athena Scripting Engine. It's the compressed if-else statement. This is the format:

<condition>` ? `<expression when true>` : `<expression when false>

The condition is using no operators, Unary operators (1 argument), or any of the comparison Binary operators (2 arguments). Whatever operator you use the arguments provided for that operator, must be both a string or both an integer in the case of binary operators, or a string or an integer in any of the other operator types. When you fail to do this, for example, when comparing a string to an integer, or when you use something else besides a string or an integer, you will get this error.
<b><u>Solution</u></b>
Make sure that whatever you put in the condition part of the code, is of the valid type integer or string. Also, when using more than one argument, make sure that for each operator, they match up in type.
<b><u>Example</u></b>
Wrong code:

`mes (MyString$ > MyInt) ? "You win" : "You lose";`

Correct code:

`mes (YourInt > MyInt) ? "You win" : "You lose";`

------------------------------------------------------------------------

#### script:query_sql: not a variable

Source Syntax: ShowError("script:query_sql: not a variable\\n");
<b><u>Cause</u></b>
You tried to pass a variable for storing results for your SQL query. The variable isn't a variable though.
<b><u>Solution</u></b>
Recheck if the variables at the end of your query_sql statement are indeed variables. Check their spelling and if they aren't commands or labels or something likewise.
<b><u>Example</u></b>
Wrong code:

`` query_sql("SELECT `name` FROM `char` WHERE `char_id` = '"+.@char_id+"'", .@$result); ``

Correct code:

`` query_sql("SELECT `name` FROM `char` WHERE `char_id` = '"+.@char_id+"'", .@result$); ``

------------------------------------------------------------------------

==== script:run_script_main: unexpected stack position stack.sp(...) != default(...) ==== Source Syntax: ShowError("script:run_script_main: unexpected stack position stack.sp(%d) != default(%d)\\n", stack-&gt;sp, stack-&gt;defsp);
<b><u>Cause</u></b>
This error means that your stack got corrupted. This is not something you can do anything about.
<b><u>Solution</u></b>
First, restart your server, and see if the error happens again. If it does occur again, then you should contact a [developer](/Staff "wikilink"), because it is likely that someone made an error in the script engine then.

------------------------------------------------------------------------

#### script:set: no player attached for player variable '...'

Source Syntax: ShowError("script:set: no player attached for player variable '%s'\\n", name);
<b><u>Cause</u></b>
Server variables are NPC variables (.) and global variables ($). In your script you used one of the non-server variables, which need a player to be attached to the script. However, there is no player attached to the script.
<b><u>Solution</u></b>
Recheck if the variable is supposed to be a non-server variable. If it is supposed to be a non-server variable, make sure that there is a player attached to the script.

------------------------------------------------------------------------

#### script:set: not a variable

Source Syntax:
Current: ShowError("script:set: not a variable\\n");
Until Rev. 10812: ShowError("script: buildin_set: not name\\n");
<b><u>Cause</u></b>
You tried to use set on something which isn't a variable. That, or you failed to provide any variable, or a variable who's name is already used by a label, function, sub-function or script command.
<b><u>Solution</u></b>
Recheck if you provided a variable to be set, as well as the variable having the correct naming requirements.
<b><u>Example</u></b>
Wrong code:

`set ,5;`

Correct code:

`set @temp, 5;`

------------------------------------------------------------------------

#### script:setarray: illegal scope

Source Syntax: ShowError("script:setarray: illegal scope\\n");
<b><u>Cause</u></b>
This error indicates that you tried to use setarray on a variable which isn't an array.
<b><u>Solution</u></b>
Recheck if the array you want to set actually is an array, and that you typed the name of the array correctly.

------------------------------------------------------------------------

#### script:setarray: not a variable

Source Syntax: ShowError("script:setarray: not a variable\\n");
<b><u>Cause</u></b>
The variable you tried to set with setarray, isn't a variable, or it isn't a legal variable name.
<b><u>Solution</u></b>
Confirm that the variable does exist, and that it obeys the official rules for names of a variable. For reference, check this link: [Variables\#Other_Important_Info Naming Variables](/Variables#Other_Important_Info_Naming_Variables "wikilink")
<b><u>Example</u></b>
Wrong code:

`setarray .1st_array[1],3,6,5;`

Correct code:

`setarray .First_array[1],3,6,5;`

------------------------------------------------------------------------

#### script:setd: no player attached for player variable '...'

Source Syntax: ShowError("script:setd: no player attached for player variable '%s'\\n", buffer);
<b><u>Cause</u></b>
Server variables are NPC variables (.) and global variables ($). In your script you used one of the non-server variables, which need a player to be attached to the script. However, there is no player attached to the script.
<b><u>Solution</u></b>
Recheck if the variable is supposed to be a non-server variable. If it is supposed to be a non-server variable, make sure that there is a player attached to the script.

------------------------------------------------------------------------

#### script:setmobdata: unknown data identifier ...

Source Syntax: ShowError("script:setmobdata: unknown data identifier %d\\n", type);
<b><u>Cause</u></b>
You wanted to change a part of a mob's data, however, that part does not exist. You can set up to 27 different parameters when it comes to mob data, of which the first 21 are explained here: [setmobdata](http://djyhnzo.freepgs.com/index.php?c=setmobdata)
<b><u>Solution</u></b>
Make sure that whatever you are trying to set, is something that exists. You should only use this line when you know what you are doing, so if you are unsure on what is wrong, simply erase the line.

------------------------------------------------------------------------

#### script:setnpcdisplay: expected a string or number

Source Syntax: ShowError("script:setnpcdisplay: expected a string or number\\n");
<b><u>Cause</u></b>
You did not provide a correct new name or view id for the NPC.
<b><u>Solution</u></b>
The format of setnpcdisplay allows you to change the name, the view ID or both of the NPC. If you change the name, provide the name before the view ID, if you are changing that as well. Also, recheck that the new view ID is a number and the new name is a string, if these are being altered.
<b><u>Example</u></b>
Wrong code:

`setnpcdisplay(strnpcinfo(0), 113, "Announcer");`

Correct code:

`setnpcdisplay(strnpcinfo(0), "Announcer", 113);`

------------------------------------------------------------------------

#### script:unitattack: unsupported source unit type ...

Source Syntax: ShowError("script:unitattack: unsupported source unit type %d\\n", unit_bl-&gt;type);
<b><u>Cause</u></b>
You can only use the unitattack command on players, monsters or pets. You tried using it on a different type of unit.
<b><u>Solution</u></b>
Recheck the unit id which you provided, if it is the UID of a player, monster or pet. These three types have a terminal UID, which gets erased when the monster dies, the pet walks away, or when the player logs out. To make sure that your error isn't caused by this as well, put some safeguards in place, like checking if the player is still online.

------------------------------------------------------------------------

#### script:warpportal: npc is needed

Source Syntax:
Current: ShowError("script:warpportal: npc is needed\\n");
Until Rev. 10812: ShowError("script:warpportal: npc is needed");
<b><u>Cause</u></b>
Warpportal is a command that can be used from inside a script to spawn a warp portal. This works different from the script type warp portal, which is permanent. One of the requirements for warpportal is that it needs to be executed from within a normal NPC. In your case, this is exactly what went wrong.
<b><u>Solution</u></b>
Make sure that your warpportal line is within a normal NPC, and not defined as a stand-alone warpportal, nor that it is inside a function, subroutine, itemscript or monsterscript.

------------------------------------------------------------------------

#### script_rid2sd: fatal error ! player not attached!

Source Syntax: ShowError("script_rid2sd: fatal error ! player not attached!\\n");
<b><u>Cause</u></b>
One of the commands you were using in your script, requires the assistance of a player. A wide variety of commands as well as certain variables, require the player to be attached to the script. This is what went wrong in your script. For example, you tried to access or set a player variable with no player attached to the script, or a command like addtimer which requires the attachment of a player.
<b><u>Solution</u></b>
In the case of a variable, make sure that either a player is attached, or in the cases that this is impossible, that you are using a NPC or global variable.
In the case of commands, also make sure that the player is attached.
If by default, a player should be attached, then the most likely option is that the player logged off. So, make some safeguards against this, by using for example the isloggedin command, to check if the player is still logged in.

------------------------------------------------------------------------

#### script_save_mapreg: Unable to lock-open file \[...\]

Source Syntax: ShowError("script_save_mapreg: Unable to lock-open file \[%s\]\\n",mapreg_txt);
<b><u>Cause</u></b>
Your mapserver tried to save the global variables to its file (save/mapreg.txt). Unfortunately, it was unable to do this, because the file is already opened by another program in the lock-mode.
<b><u>Solution</u></b>
Recheck if no other program (like a text-editor) is using the file, and make sure that when no other program is using it, that the file has been closed properly.

------------------------------------------------------------------------

#### startnpctimer: invalid argument type \#1 (needs be int or string)).

Source Syntax: ShowError("startnpctimer: invalid argument type \#1 (needs be int or string)).\\n");
<b><u>Cause</u></b>
Startnpctimer has several formats. The different kinds of formats allow you to either attach it to another NPC, or to let it start at a certain value. The value or the NPC name you provided is incorrect, the mapserver does not recognize it as a string or integer.
<b><u>Solution</u></b>
Recheck if you are giving the correct argument to the command, make sure it is an integer or a string. In the case of using a variable, make sure that the variable contains correct data.

------------------------------------------------------------------------

#### stopnpctimer: invalid argument type \#1 (needs be int or string)).

Source Syntax: ShowError("stopnpctimer: invalid argument type \#1 (needs be int or string)).\\n");
<b><u>Cause</u></b>
Stopnpctimer has several formats. The different kinds of formats allow you to either attach it to another NPC, or to let it start at a certain value. The value or the NPC name you provided is incorrect, the mapserver does not recognize it as a string or integer.
<b><u>Solution</u></b>
Recheck if you are giving the correct argument to the command, make sure it is an integer or a string. In the case of using a variable, make sure that the variable contains correct data.

------------------------------------------------------------------------

#### unget_com can back only 1 data

Source Syntax: ShowError("unget_com can back only 1 data\\n");
<b><u>Cause</u></b>
As most code that is inside the scripting engine's main part, this error seems unlikely to be caused by your scripts. What exactly causes it to trigger is unknown to me.
<b><u>Solution</u></b>
Your best chance is to get support in the Scripting Support Forum, or to contact one of the [developers](/developers "wikilink").

------------------------------------------------------------------------

#### unknown command : ... @ ...

Source Syntax: ShowError("unknown command : %d @ %d\\n",c,pos);
<b><u>Cause</u></b>
This error indicates a source problem. It means, that the script engine generated a byte instruction out of some part of your script, which is undefined in the runtime part of the engine.
<b><u>Solution</u></b>
Report it to core developers, together with your script, to get the source issue fixed.

------------------------------------------------------------------------

#### wrong item ID : countitem(...)

Source Syntax: ShowError("wrong item ID : countitem(%i)\\n", nameid);
<b><u>Cause</u></b>
You provided an invalid item id for countitem. This error is triggered when you provide an item id lower than 500.
<b><u>Solution</u></b>
Check if you didn't enter a faulty item id, and correct it when needed.
<b><u>Example</u></b>
Wrong code:

`if(countitem(400) < 1) close;`

Correct code:

`if(countitem(500) < 1) close;`

------------------------------------------------------------------------

#### wrong item ID : countitem2(...)

Source Syntax: ShowError("wrong item ID : countitem2(%i)\\n", nameid);
<b><u>Cause</u></b>
You provided an invalid item id for countitem. This error is triggered when you provide an item id lower than 500.
<b><u>Solution</u></b>
Check if you didn't enter a faulty item id, and correct it when needed.
<b><u>Example</u></b>
Wrong code:

`if(countitem2(400,1,0,0,0,0,0,0) < 1) close;`

Correct code:

`if(countitem2(500,1,0,0,0,0,0,0) < 1) close;`

------------------------------------------------------------------------

#### wrong item ID : equipitem(...)

Source Syntax: ShowError("wrong item ID : equipitem(%i)\\n",nameid);
<b><u>Cause</u></b>
You tried to equip an item with equipitem, which doesn't exist.
<b><u>Solution</u></b>
Check if you entered the correct item id, and also check if it exists in item_db.txt or item_db2.txt or when using SQL item databases, in the database item_db and item_db2.

------------------------------------------------------------------------

### Fatal Errors

All fatal errors are listed in this section.
==== npc_addeventtimer: out of memory ! ==== Source Syntax: ShowFatalError("npc_addeventtimer: out of memory !\\n");
<b><u>Cause</u></b>
Your script tried to start another eventtimer. Unfortunately your server's computer has run out of memory, so it cannot create this new timer.
<b><u>Solution</u></b>
Try freeing up more memory. However, if the problem still occurs, then the real cause might be in faulty scripting. Check the script if it loops a lot with timers located inside the loops. Try to minimize the amount of loops or even better, avoid them when using timer script commands.

------------------------------------------------------------------------

#### npc_event_export: label name error !

Source Syntax: ShowFatalError("npc_event_export: label name error !\\n");
<b><u>Cause</u></b>
This error occurs when you have a npc event label with an invalid size of the name. NPC event labels always start with On. The size of the name of the event label is each character after On and before the ':'. When this amount of characters is 0 (in the case of "On:") or bigger than the constant NameLength, which is 23 or 24 (in the case of "OnAbcdefghijklmnopqrstuvwxyz:"), your mapserver will be unable to create the npc event label, and therefor crash.
<b><u>Solution</u></b>
Rename the event labels that are bugged. Make sure that they actually have a name between the On and ":" part, and that this name does not exceed 23 characters.

------------------------------------------------------------------------

#### npc_event_export: out of memory !

Source Syntax: ShowFatalError("npc_event_export: out of memory !\\n");
<b><u>Cause</u></b>
This error occurs when the server does not have enough free memory to allocate a new npc event label. (These are the labels that start with On.)
<b><u>Solution</u></b>
Try to free up more memory, or add new memory to your system. If this does not solve the problem, then you will have to consider to use less npc event labels. This can be accomplished by either erasing NPCs that contain them, or by optimizing your npc event labels.

------------------------------------------------------------------------

#### npc_timerevent_import: out of memory !

Source Syntax: ShowFatalError("npc_timerevent_import: out of memory !\\n");
<b><u>Cause</u></b>
This error occurs when the server does not have enough free memory left to allocate space for an OnTimer: label.
<b><u>Solution</u></b>
Free up more memory, or remove OnTimer labels that you do not use.

------------------------------------------------------------------------

### Parsing Errors

All parsing errors are listed in this section.
==== expect ';' or '{' at function syntax ==== Source Syntax: disp_error_message("expect ';' or '{' at function syntax",p);
<b><u> Cause</u></b>
An in-script function was used or declared in an invalid manner.
<b><u> Solution</u></b>
You tried to write or use an in-script function. The normal format for this is one of the following two:

`function test; // Calls upon in-script function test.`
`function   test    { // Declaration of a function including needed code.`
`   // Function code goes here.`
`}`

In your case, the script parser encountered something else than the allowed { or ; after the function's name. Recheck your in-script function, and make sure it either has a ; or a { at the end of the line.

------------------------------------------------------------------------

#### need '('

Source Syntax: disp_error_message("need '('",p);
<b><u> Cause</u></b>
In your script, there is a function that you are trying to call. This function requires it's arguments to be between round brackets. Your script is lacking at least the left one ('('), and most likely both.
<b><u> Solution</u></b>
Search inside your script for the function call displayed by the error. Fix it by making sure there are parentheses around the arguments.
<b><u> Example</u></b>
Wrong code:

`...`
`set .var, SF_DummyFunction 5, 7;`
`...`

Correct code is:

`...`
`set .var, SF_DummyFunction(5, 7);`
`...`

------------------------------------------------------------------------

#### not found '{'

Source Syntax: disp_error_message("not found '{'",p);
<b><u>Cause</u></b>
The header of your script or function is missing a '<b>{</b>'. This left curly bracket specifies the start of the body of the script, and must be on the same line as your header.
<b><u>Solution</u></b>
If you forgot to place a { at all, then place it at the end of the header line. If you placed the opening curly bracket at the next line, then move it until it is at the same line as the header.
<b><u>Example</u></b>
Wrong code:

`prontera,200,200,4`<tab>`script`<tab>`Dummy`<tab>`46,`
`{`
`   mes "hi";`
`   close;`
`}`

It should be:

`prontera,200,200,4`<tab>`script`<tab>`Dummy`<tab>`46,{`
`   mes "hi";`
`   close;`
`}`

------------------------------------------------------------------------

#### parse_callfunc: callsub has no arguments, please review it's definition

Source Syntax: disp_error_message("parse_callfunc: callsub has no arguments, please review it's definition",p);
<b><u>Cause</u></b>
In the words of one of the devs: "Someone fucked up the script engine." This means, that if you get this error, which is highly unlikely, that you probably did nothing wrong.
<b><u>Solution</u></b>
When you encounter this problem though, please report it to the core developers. Tell them what you did that caused it (i.e. show the script, tell them what you did with the script, just loading or using it or whatever, and of course, when the bug happens).

------------------------------------------------------------------------

#### parse_callfunc: DEBUG last curly is not an argument list

Source Syntax: disp_error_message("parse_callfunc: DEBUG last curly is not an argument list",p);
<b><u>Cause</u></b>
The parsing of function parameter lists is bugged in the script engine. (In essence, you should never get this error.)
<b><u>Solution</u></b>
There is no known solution to this. What is advised by the Developers themselves is to report this to the devs. When doing this, also provide your script that is causing this error.

------------------------------------------------------------------------

#### parse_callfunc: expected ')' to close argument list

Source Syntax: disp_error_message("parse_callfunc: expected ')' to close argument list",p);
<b><u>Cause</u></b>
This error occurs when you are calling a function or something likewise, which uses round brackets around the arguments, but you forgot to enter the closing rounding bracket.
<b><u>Solution</u></b>
Simply go to the specified bugged function call, and count if the amount of left round brackets match the amount of right round brackets. Change them when needed.
<b><u>Example</u></b>
Wrong usage:

`...`
`set @temp, SF_DummyFunction(5, 7;`
`...`

As you can see, 1 (, but no ). Correct line would be:

`set @temp, SF_DummyFunction(5, 7);`

------------------------------------------------------------------------

#### parse_callfunc: not enough arguments, expected ','

Source Syntax: disp_error_message2("parse_callfunc: not enough arguments, expected ','", p, script_config.warn_func_mismatch_paramnum);
<b><u>Cause</u></b>
When calling upon a predefined function, you need to meet the exact amount of arguments. In this case, you did not have enough arguments.
<b><u>Solution</u></b>
Make sure the bugged function has the right amount of arguments. Look at it's template, and see if the amount of arguments match.

------------------------------------------------------------------------

#### parse_curly_close: unexpected string

Source Syntax: disp_error_message("parse_curly_close: unexpected string",p);
<b><u>Cause</u></b>
We are not 100% sure, but this might happen if you place a normal string after you put the closing curly of the NPC. Again, not 100% sure, but the developers say that this is one of those rare cases that shouldn't occur. However, when it does occur, please use the scripting support forum if you cannot figure out how to fix it. Another possibility as a cause, is that you have too many right curly brackets ('}').
<b><u>Solution</u></b>
The probable solution is to erase the string or right curly bracket that the mapserver shows you. Or, recount your left and right curly brackets, and make sure they are all in the right spot.

------------------------------------------------------------------------

#### parse_expr: unexpected char

Source Syntax: disp_error_message("parse_expr: unexpected char",p);
<b><u>Cause</u></b>
This error occurs when the server detects a character in your script that shouldn't be there. This can happen when you have misplaced one of the following characters: ')', ';', ':', '\[', '\]' or '}'.
<b><u>Solution</u></b>
Either move or remove the wrong placed character, or fix the text/arguments that are forgotten in front of these characters.
<b><u>Example</u></b>
Example of what might cause this error:

`...`
`set .@[0], 5;`
`...`

What the line can be:

`set .@temp[0], 5;`

------------------------------------------------------------------------

#### parse_line: expect command, missing function name or calling undeclared function

Source Syntax: disp_error_message("parse_line: expect command, missing function name or calling undeclared function",p);
<b><u>Cause</u></b>
This is probably happening when you are trying to call to a function that simply does not exist.
<b><u>Solution</u></b>
Make sure the function you are trying to reach, actually exists. If it exists, make sure you did not make any typos. And if it didn't exist, create the function, or remove the line.

------------------------------------------------------------------------

#### parse_line: need ')'

Source Syntax: disp_error_message("parse_line: need ')'",p);
<b><u>Cause</u></b>
This error is most commonly seen when your if, for or while statement lacks a closing round bracket.
<b><u>Solution</u></b>
Check your for, if or while statement, and make sure the amount of opening round brackets match the amount of closing round brackets. Also, with if and while, make sure that the entire condition that you want to check, is closed in by at least one ( and one ). Extra brackets are not a sin, too few are.
<b><u>Example</u></b>
Wrong code:

`if(i > 10 end;`

This should be:

`if(i > 10) end;`

------------------------------------------------------------------------

#### parse_line: need ';'

Source Syntax: disp_error_message("parse_line: need ';'",p);
<b><u>Cause</u></b>
One of the most common errors. There are actually two versions of this one. One that only occurs within the first line of a for-statement, the other one being, simply forgetting a ';' at the end of the line.
<b><u>Solution</u></b>
In case of a for-statement going bad, please make sure it upholds this format: for(<initiation>;<condition>;<iteration>). In case of anything else, then the error is 99 out of 100 times, not on the line the script parser tells you. It is often a forgotten ; in the line above. Make sure this is the case, and add it there.
<b><u>Example</u></b>
Wrong code:

`set @temp, 5`
`close;`

Correct code should be:

`set @temp, 5;`
`close;`

------------------------------------------------------------------------

#### parse_simpleexpr: unexpected character

Source Syntax: disp_error_message("parse_simpleexpr: unexpected character",p);
<b><u>Cause</u></b>
The script engine was expecting a word (the name of a variable, label, function or something like that) and found something else.
<b><u>Solution</u></b>
Make sure that you have typed the right word, and did not use invalid characters.
<b><u>Example</u></b>
Probably example of wrong code:

`mes "2 + 2 equals "+ ( + 2) +".";`
`mes "I know math!";`

Correct code:

`mes "2 + 2 equals "+ (2 + 2) +".";`
`mes "I know math!";`

------------------------------------------------------------------------

#### parse_simpleexpr: unexpected eof @ string

Source Syntax: disp_error_message("parse_simpleexpr: unexpected eof @ string",p);
<b><u>Cause</u></b>
Your string is not properly closed. In fact, there is nothing behind the string. This can be caused when you are editing your file, and save your progress while you were typing a string, and then ran this script.
<b><u>Solution</u></b>
Close the string like it should be closed (with a "), or remove the line all together if it shouldn't be there. Also close up the script all together, because eof means End of File. So even if you just fix this bug, your NPC is still bugged.
<b><u>Example</u></b>
Wrong code:

`...`
`mes "Bye`
<file ends>

Right code:

`...`
`mes "Bye";`
`close;`
`}`

------------------------------------------------------------------------

#### parse_simpleexpr: unexpected expr end

Source Syntax: disp_error_message("parse_simpleexpr: unexpected expr end",p);
<b><u>Cause</u></b>
This can happen in a variety of cases. They call come down to not closing a string, command or condition correct.
<b><u>Solution</u></b>
Make sure that your string or command is properly closed. If this does not apply, make sure that your condition is set up correctly.
<b><u>Example</u></b>
Wrong code:

`set @total, 5 + ;`

Correct code:

`set @total, 5;`

or

`set @total, 5 + 1;`

------------------------------------------------------------------------

#### parse_simpleexpr: unexpected newline @ string

Source Syntax: disp_error_message("parse_simpleexpr: unexpected newline @ string",p);
<b><u>Cause</u></b>
You either forgot to close your string, or pressed return, and typed the rest on a new line. Unfortunately, a string needs to be closed on the same line.
<b><u>Solution</u></b>
Properly close the string, or divide it in multiple parts using: "string part 1" + "string part 2" etc.
<b><u>Example</u></b>
Wrong code:

`mes "Hello there.`
`     My name is Nienke.";`

Corrected code:

`mes "Hello there. My name is Nienke.";`

or

`mes "Hello there." +`
`    "My name is Nienke.";`

------------------------------------------------------------------------

#### parse_simpleexpr: unmatch ')'

Source Syntax: disp_error_message("parse_simpleexpr: unmatch ')'",p);
<b><u>Cause</u></b>
The amount of opening round brackets does not match the amount of closing round brackets. Again, this can happen in a wide variety of cases.
<b><u>Solution</u></b>
Count the amount of brackets that you have. Make sure each opening bracket has a closing bracket.
<b><u>Example</u></b>
Wrong code:

`set @total, 5 * (6 + (5 * 5);`

Correct code:

`set @total, 5 * (6 + (5 * 5));`

or

`set @total, 5 * (6 + 5 * 5);`

------------------------------------------------------------------------

#### parse_simpleexpr: unmatch '\]'

Source Syntax: disp_error_message("parse_simpleexpr: unmatch '\]'",p);
<b><u>Cause</u></b>
This error occurs when you forgot to close off the element part of an array.
<b><u>Solution</u></b>
To fix this, you need to ask yourself first: Did I want an array at this point? If not, remove the opening square bracket. If you did, make sure the amount of opening square brackets match the amount of closing square brackets.
<b><u>Example</u></b>
Wrong code:

`set @temp[0, 5;`

Correct code:

`set @temp[0], 5;`

------------------------------------------------------------------------

#### parse_subexpr: need ':'

Source Syntax: disp_error_message("parse_subexpr: need ':'", p-1);
<b><u>Cause</u></b>
This errors occurs, when you use a compact if statement, and forgot the : to separate the true and false statements. A compact if statement looks like this:

<condition>` ? `<expression when true>` : `<expression when false>

<b><u>Solution</u></b>
Confirm you wanted to use the compact if statement. If this is the case, find where you forgot to add the ':'. If it isn't the case, make sure that the question mark triggering this statement is not there, or erase the entire line.
<b><u>Example</u></b>
Wrong code:

`mes "You are part of team " + ( (a == 1) ? "Blue""Red" );`

Correct code:

`mes "You are part of team " + ( (a == 1) ? "Blue" : "Red" );`

------------------------------------------------------------------------

#### parse_syntax: 'case' label not integer

Source Syntax: disp_error_message("parse_syntax: 'case' label not integer",p);
<b><u>Cause</u></b>
The format for a case label is: "case \#:", where \# must be an integer value. If this is not the case, the mapserver will throw this error at you. The Athena Scripting Language does **NOT** support "case <string>:" and possibly not even "case <character>:".
<b><u>Solution</u></b>
Change whatever you had between the case and ':' to a real integer value instead.
<b><u>Example</u></b>
Wrong code:

`switch(@a$) {`
`   case "Hi":`

Correct code:

`switch(@a) {`
`   case 1:`

------------------------------------------------------------------------

#### parse_syntax: dup 'case'

Source Syntax: disp_error_message("parse_syntax: dup 'case'",p);
<b><u>Cause</u></b>
Inside the same switch, one 'case label' exists more than one time. This error is like the normal duplicate label error. Two of the same named labels exists in the same piece of code, in this case, the switch.
<b><u>Solution</u></b>
Remove the duplicated case label, and when needed, merge their both codes.
<b><u>Example</u></b>
Wrong code:

`case 1:`
`   set @a, 5;`
`   break;`
`case 1:`
`   set @b, 5;`
`   break;`

Correct code:

`case 1:`
`   set @a, 5;`
`   set @b, 5;`
`   break;`

------------------------------------------------------------------------

#### parse_syntax: dup 'default'

Source Syntax: disp_error_message("parse_syntax: dup 'default'",p);
<b><u>Cause</u></b>
Same cause as the error right above this one. There is a duplicated label named default within the same switch.
<b><u>Solution</u></b>
Remove the second default label, and when needed, merge the code.
<b><u>Example</u></b>
Wrong code:

`default:`
`   set @a, 5;`
`   break;`
`default:`
`   set @b, 5;`
`   break;`

Correct code:

`default:`
`   set @a, 5;`
`   set @b, 5;`
`   break;`

------------------------------------------------------------------------

#### parse_syntax: expect ':'

Source Syntax: disp_error_message("parse_syntax: expect ':'",p);
<b><u>Cause</u></b>
The case label, inside the switch command, is missing the ':'. This is exactly the same as with normal variables.
<b><u>Solution</u></b>
Simply add the colon after the case label. Or, when the case label is not needed, simply remove it.
<b><u>Example</u></b>
Wrong code:

`case 1`
`   set @a, 5;`
`   break;`

Correct code:

`case 1:`
`   set @a, 5;`
`   break;`

------------------------------------------------------------------------

#### parse_syntax: expect space ' '

Source Syntax: disp_error_message("parse_syntax: expect space ' '",p);
<b><u>Cause</u></b>
Another case label error. The format for a case label is: "case \#:", where \# is an integer value. The format dictates that there needs to be a space between the word "case" and the integer value. This space is missing in your script.
<b><u>Solution</u></b>
Add the space between "case" and the number.
<b><u>Example</u></b>
Wrong code:

`case1:`
`   set @a, 5;`
`   break;`

Correct code:

`case 1:`
`   set @a, 5;`
`   break;`

------------------------------------------------------------------------

#### parse_syntax: need '('

Source Syntax: disp_error_message("parse_syntax: need '('",p);
<b><u>Cause</u></b>
Your for-line is not following the default format. The format is: for(<initiation>;<condition>;&lt;iteration);. You are missing the '('.
<b><u>Solution</u></b>
Remove the for-statement all together, if it is not supposed to be there, or add the missing left round bracket.
<b><u>Example</u></b>
Wrong code:

`for set @a,5; @a < 10; set @a, @a + 1) {`

Correct code:

`for(set @a,5; @a < 10; set @a, @a + 1) {`

------------------------------------------------------------------------

#### parse_syntax: need ':'

Source Syntax: disp_error_message("parse_syntax: need ':'",p);
<b><u>Cause</u></b>
Missing the ':' behind the switch label named "default".
<b><u>Solution</u></b>
Add the missing colon directly after default. (Or remove the default label all together.)
<b><u>Example</u></b>
Wrong code:

`default`
`   break;`

Correct code:

`default:`
`   break;`

------------------------------------------------------------------------

#### parse_syntax: need ';'

Source Syntax: disp_error_message("parse_syntax: need ';'",p);
<b><u>Cause</u></b>
One of the most common errors. There are actually two versions of this one. One that only occurs within the first line of a for-statement, the other one being, simply forgetting a ';' at the end of the line.
<b><u>Solution</u></b>
In case of a for-statement going bad, please make sure it upholds this format: for(<initiation>;<condition>;<iteration>). In case of anything else, then the error is 99 out of 100 times, not on the line the script parser tells you. It is often a forgotten ; in the line above. Make sure this is the case, and add it there.
<b><u>Example</u></b>
Wrong code:

`set @temp, 5`
`close;`

Correct code should be:

`set @temp, 5;`
`close;`

------------------------------------------------------------------------

#### parse_syntax: need 'while'

Source Syntax: disp_error_message("parse_syntax: need 'while'",p);
<b><u>Cause</u></b>
Your Do-command is missing the while-command after the closing '}'. Format for this command is: do { <statements> } while (<condition);
<br>
<b><u>Solution</u></b>
Add the missing while-command and when needed, the condition.
<b><u>Example</u></b>
Wrong code:

`do {`
`   set @a, @a + 1;`
`}`

Correct code:

`do {`
`   set @a, @a + 1;`
`} while (@a < 100);`

------------------------------------------------------------------------

#### parse_syntax: unexpected 'continue'

Source Syntax: disp_error_message("parse_syntax: unexpected 'continue'",p);
<b><u>Cause</u></b>
Continue can be only used within looping commands, like for, do .. while and while. It simply means, ignore the rest, start a new round. Your continue-command however, is placed outside one of these looping commands.
<b><u>Solution</u></b>
Move continue; to inside the looping command you wanted it to use for. If this is not what you wanted, then erase the line.
<b><u>Example</u></b>
Wrong code:

`for(set @i, 0; @i < 10; set @i, @i + 1) {`
`  if(@My_Numbers[@i] != $Winning_Numbers[@i]) {`
`     set @i, @i + 1;`
`     set Points, Points - 1;`
`  }`
`  set Points, Points + 1;`
`}`
`continue;`

Correct code:

`for(set @i, 0; @i < 10; set @i, @i + 1) {`
`  if(@My_Numbers[@i] != $Winning_Numbers[@i]) continue;`
`  set Points, Points + 1;`
`}`

------------------------------------------------------------------------

#### parse_syntax: unexpected 'default'

Source Syntax: disp_error_message("parse_syntax: unexpected 'default'",p);
<b><u>Cause</u></b>
This happens when you place the "default:" label outside of a switch.
<b><u>Solution</u></b>
Erase the default label or move it inside the switch you wanted to use it for.
<b><u>Example</u></b>
The example in the error right above this one can be applied for this one as well.

------------------------------------------------------------------------

#### parse_syntax: unexpected 'break'

Source Syntax: disp_error_message("parse_syntax: unexpected 'break'",p);
<b><u>Cause</u></b>
The break; command is only supposed to be used in looping functions or functions that use curly brackets (like if or switch). It will make you jump outside of the statement. In this case, this break; is not located in such a function.
<b><u>Solution</u></b>
Remove the break; or replace it by an end; if you want to end the script.
<b><u>Example</u></b>
Wrong code:

`-`<tab>`script`<tab>`Dummy`<tab>`-1,{`
`   OnInit:`
`      set $Blah, 14;`
`      break;`
`   ....`

Correct code:

`-`<tab>`script`<tab>`Dummy`<tab>`-1,{`
`   OnInit:`
`      set $Blah, 14;`
`      end;`
`   ....`

------------------------------------------------------------------------

#### parse_syntax: unexpected 'case'

Source Syntax: disp_error_message("parse_syntax: unexpected 'case' ",p);
<b><u>Cause</u></b>
This happens when you place the "case \#:" label outside of a switch.
<b><u>Solution</u></b>
Erase the case label or move it inside the switch you wanted to use it for.
<b><u>Example</u></b>
The example in the third error above this one can be applied for this one as well.

------------------------------------------------------------------------

#### parse_syntax:function: function name is missing or invalid

Source Syntax: disp_error_message("parse_syntax:function: function name is missing or invalid", p);
<b><u>Cause</u></b>
The name you are using in the function line is not valid, or is there not at all.
<b><u>Solution</u></b>
Use a correct name for the function. The same rules abide as for labels and variable names.
<b><u>Example</u></b>
Wrong code:

`function 1stFunction;`
`function;`

Correct code for both:

`function SF_Function01;`

------------------------------------------------------------------------

#### script:add_word: invalid word. A word consists of underscores and/or alphanumeric characters, and valid variable prefixes/postfixes.

Source Syntax: disp_error_message("script:add_word: invalid word. A word consists of underscores and/or alphanumeric characters, and valid variable prefixes/postfixes.", p);
<b><u>Cause</u></b>
This happens when a word does not meet the standard format. Like the error says: A word consists of underscores and/or alphanumeric characters, and valid variable prefixes/postfixes.
<b><u>Solution</u></b>
Change the name to meet the requirements.

------------------------------------------------------------------------

#### set_label: dup label

Source Syntax: disp_error_message("set_label: dup label ",script_pos);
<b><u>Cause</u></b>
This label already exists. It is not allowed to have the same label more than once, within the same NPC, itemscript, monsterscript, function or sub.
<b><u>Solution</u></b>
Remove or rename one of the two labels to fix this. Also change the code depending on the label that is going to be changed or removed.
<b><u>Example</u></b>
Wrong code:

`...`
`goto Hello;`
`...`
`Hello:`
`   mes "Hello";`
`   close;`
`Hello:`
`   mes "Hi";`
`   close;`

Correct code:

`...`
`goto Hello;`
`...`
`Hello:`
`   mes "Hello";`
`   close;`

------------------------------------------------------------------------

#### set_label: invalid label name

Source Syntax: disp_error_message("set_label: invalid label name",script_pos);
<b><u>Cause</u></b>
You are trying to use the name of a reserved variable or constant as a label name. This is not allowed.
<b><u>Solution</u></b>
Change the label name into something else.
<b><u>Example</u></b>
Wrong code:

`goto BaseLevel;`
`...`
`BaseLevel:`

Correct code:

`goto L_BaseLevel;`
`...`
`L_BaseLevel:`

------------------------------------------------------------------------

#### unexpected end of script

Source Syntax: disp_error_message("unexpected end of script",p);
<b><u>Cause</u></b>
The script parser encountered an unexpected end of the script without having a matching amount of paired curly brackets and without encountering the end tag.
<b><u>Solution</u></b>
Recheck your script and make sure that you have the closing curly bracket at the end of your script. Also count your curly brackets. Make sure that there is a matching } for each { that you have.

------------------------------------------------------------------------

### Obsolete Errors

This section will cover all errors that used to exist in the past, but are not represented anymore in today's revision. (So, there is not even a replacement, they were completely erased.)

#### Up to Revision 11859

------------------------------------------------------------------------

===== getequipid: sd == NULL ===== Source Syntax: ShowError("getequipid: sd == NULL\\n");
<b><u>Cause</u></b>
You tried to use getequipid, without having a player attached to the script.
<b><u>Solution</u></b>
Make sure that the command is only used when a player is attached to the script. If needed, when using timed events for example, check whether the player is still online or not.

------------------------------------------------------------------------

##### script:get_val error, cannot access player variable '...', defaulting to ""

Source Syntax: ShowError("script:get_val: cannot access player variable '%s', defaulting to \\"\\"\\n", name);
<b><u>Cause</u></b>
You tried accessing a player type variable (Temporal or permanent player variable, account variable or global account variable) without having a player attached to the script. Because this variable was of the type String, the mapserver converted it to an empty string "".
<b><u>Solution</u></b>
Make sure that you actually have a player attached to your script when trying to access player-type variables.

------------------------------------------------------------------------

##### script:get_val error, cannot access player variable '...', defaulting to 0

Source Syntax: ShowError("script:get_val: cannot access player variable '%s', defaulting to 0\\n", name);
<b><u>Cause</u></b>
You tried accessing a player type variable (Temporal or permanent player variable, account variable or global account variable) without having a player attached to the script. Because this variable was of the type Integer, the mapserver converted it to 0.
<b><u>Solution</u></b>
Make sure that you actually have a player attached to your script when trying to access player-type variables.

------------------------------------------------------------------------

#### Up to Revision 11778

------------------------------------------------------------------------

##### buildin_fakenpcname: Invalid look value ...

Source Syntax: ShowError("buildin_fakenpcname: Invalid look value %d\\n",look);
<b><u>Cause</u></b>
With the fakenpcname command, you can not only change the name into a new name. You can also adjust the look. This is what you attempted to do, but failed, because you provided an invalid look value.
<b><u>Solution</u></b>
Change the look value (third argument) in such a way that it fits in the boundaries. The minimum value is -32768 and the maximum value is 32767.
<b><u>Example</u></b>
Wrong code:

`fakenpcname "My NPC","Your NPC",600000;`

Correct code:

`fakenpcname "My NPC","Your NPC",32767;`

------------------------------------------------------------------------

#### Up to Revision 11501

------------------------------------------------------------------------

##### script:skip_space: end of file while parsing block comment. expected \*/

Source Syntax: disp_error_message("script:skip_space: end of file while parsing block comment. expected "CL_BOLD"\*/"CL_NORM, p);
<b><u>Cause</u></b>
A comment block was opened but never closed. The server encountered the end of the file before finding the closing tag for the comment block. A comment block starts with /\* and everything after it, including on new lines, will be regarded as comments, until it encounters \*/.
<b><u>Solution</u></b>
Add the \*/ at the end of your comment block, to fix this error.
<b><u>Example</u></b>
Wrong code:

`/* Tralalalala`
`   lalalalala`
`   Oops, end of the file.`

Correct code:

`/* Tralalalala`
`   lalalalala`
`   Oops, end of the file. */`

------------------------------------------------------------------------

#### Up to Revision 10842

------------------------------------------------------------------------

##### get_val error, cannot access player variable '...'

Source Syntax: ShowError("get_val error, cannot access player variable '%s'\\n", name);
<b><u>Cause</u></b>
You tried accessing a player type variable (Temporal or permanent player variable, account variable or global account variable) without having a player attached to the script.
<b><u>Solution</u></b>
Make sure that you actually have a player attached to your script when trying to access player-type variables.

------------------------------------------------------------------------

##### script:menu: argument \#... (from 1) is not a string or compatible.

Source Syntax:
Until Rev. 10842: ShowError("script:menu: argument \#%d (from 1) is not a string or compatible.\\n", (i - 1));
Until Rev. 10812: ShowError("script:menu: argument \#%d (from 1) is not a string or compatible (op=%s).\\n", (i - 1), script_op2name(data-&gt;type));
<b><u>Cause</u></b>
This error should occur when the given argument is not a string nor an integer. (Will be fixed in revision ...)
<b><u>Solution</u></b>
Check if what you provided as a menu option is a real string or an integer. Correct it if needed.

------------------------------------------------------------------------

#### Up to Revision 10812

------------------------------------------------------------------------

##### script: getelementofarray (operator\[\]): param1 not name !

Source Syntax: ShowError("script: getelementofarray (operator\[\]): param1 not name !\\n");
<b><u>Cause</u></b>
The variable name which you provided (the first argument of getelementofarray) is not a valid variable name.
<b><u>Solution</u></b>
Make sure that the variable name is using the correct syntax. For a full set of rules on variable naming, check the [appropriate article](/Variables "wikilink").
<b><u>Example</u></b>
Wrong code:

`set @result, getelementofarray(1starray,3);`

Correct code:

`set @result, getelementofarray(firstarray,3);`

------------------------------------------------------------------------

[Category:Debugging](/Category:Debugging "wikilink") [Category:Scripting](/Category:Scripting "wikilink")