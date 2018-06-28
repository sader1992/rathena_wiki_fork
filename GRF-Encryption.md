Preparation
===========
- **[GRF Editor](https://rathena.org/board/files/file/2766-grf-editor/)**, if you're not familiar with this software, it is the best **GRF Management Tool** ever coded.
- The files you want to protect, the encryption is made by file so, there's no need to encrypt the whole GRF.
- Your Hexed must be **2012-04-10** or above, it won't work on **2010 Clients**.
- Decide your **Hexed** filename, it's essential for the encryption to work.

Generating Encryption Key
=========================
**GRF Editor** uses a **Key Encryption Method**, what means that your protection is based on a password.
Choose a password you'll remember or note it somewhere, you won't be able to decrypt your files without it and always save a Backup of the files you'll encrypt.

Password chosen, you'll need to generate the **DLL**, the one that will allow your **Client** to read encrypted files.

Open the **GRF Editor** and navigates on the top menu to **Tools** > **GRF Encryption**, you'll see the window below. 

![](https://i.imgur.com/rb17MD4.png)

First, Input your Key on the **Encryption Password** field.
Next, select your Client on the **Client Path** field, it is needed for the DLL to be coded to its filename or be modified if needed.

**IMPORTANT:** The Client being asked here is for the Hexed, **IT IS NOT** the Patcher, Launcher or Loader.

The name of the DLL can also be changed, it will output a modified Hexed of ready to read it.
With everything set, click in Generate File(s), and it will pop up a folder where your DLL has been generated, add/replace the one in your Client folder. 

﻿Encrypting Files﻿
================
Files can now be encrypted. 

![](https://i.imgur.com/YHXLCJs.png)

Open your GRF, GPF or THOR, select the files you want to protect.
Right-click it and select **EncryptIon** > **Encrypt**.

Enter the **Password** you previously defined, confirm and the file will be highlighted in Orange.

![](https://i.imgur.com/MUg1W6H.png)

The colour might not show up when you're working on a THOR file or opens a GRF/THOR previously encrypted, that's normal behaviour.

Once the GRF or THOR is saved, you won't be able to read the file.
Normally an error will pop, but you can test it in game, if you've done it correctly, it will be displayed properly.

As far as I've tested, the **Encrypted** Files works in the DATA folder if extracted.

If you want to Encrypt or Decrypt a whole GRF, you can select **Tools** > **GRF Encryption** with the GRF open by the software and choose the options Encrypt GRF or Decrypt GRF.
You will be asked for the Key, and then It'll run the process through the entire GRF and export it to a new folder.

The same process can be made with THOR files, even if it displays any reading error, patched Encrypted files will work.