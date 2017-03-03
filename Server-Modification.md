You can find here some information to start making server-side source modifications.

# How rAthena works

rAthena has a multi-process architecture. It runs three different processes: **login-server**, **char-server** and **map-server**.

## Login Server

**Login server** **:** receives the login packet, checks if account exists and if the password is correct. If all is OK, the connection is then passed to the **char-server**.

## Char-Server

**Char-server** **:** controls all the character related, Guild, party, pet, inventory etc.

## Map-Server

The last one is the **map-server**, which controls char and NPC position, chats, skills, exp etc.

# Source Modifications
Before you start modifying rA, you should take a look first at the src/ folder. Remember, it's necessary to [re-compile](Compiling) rAthena after a source modification. You can also find information about [packets](packets).
