---
layout:     post
title:      Default HEC-RAS Version 
date:       2024-05-29 11:11:11
summary:    ChatGPT helps me set the correct HEC-RAS version to open .prj files.
categories: blog
---

This was driving me ever so slightly nuts for a little while.
I've had [HEC-RAS](https://www.hec.usace.army.mil/software/hec-ras/)
6.4.1 on my work laptop (Windows 10) and recently
installed version 6.5, too. Previously I set my machine to open 
`.prj` files with HEC-RAS 6.4.1. I've been wanting them to open with version
6.5 by default, but no matter what I did they were still opening with
6.4.1.

I figured there was probably some system registry setting that
would allow me to set `.prj` files to open with HEC-RAS 6.5 instead.
I've been leaning heavily on ChatGPT for technical issues like this
to avoid digging through documentation and StackOverflow answers,
and it didn't disappoint.

Here are the instructions ChatGPT landed on after a couple rounds of
back-and-forth...

### Step-by-Step Instructions:

1. **Navigate to UserChoice Key:**
   - Go to:
     ```
     HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.prj\UserChoice
     ```
   
2. **Change the ProgId:**
   - In the `UserChoice` key, find the `ProgId`. This tells Windows which application to use for opening `.prj` files.
   - Since the `ProgId` is currently set to `prj_auto_file`, you need to ensure that this is linked to the correct executable path in another part of the registry.

3. **Modify the Default Program in `prj_auto_file`:**
   - Go to:
     ```
     HKEY_CLASSES_ROOT\prj_auto_file\shell\open\command
     ```
   - Check the default value here—it should be pointing to the executable for HEC-RAS. This is where you can specify the path to the new version of the application. If this key does not exist, you will need to create it.

### Create or Modify the Command Key:
If the path needs to be updated or created, follow these steps:

1. **Navigate or Create Keys:**
   - Go to `HKEY_CLASSES_ROOT`
   - Look for a key named `prj_auto_file`. If it doesn’t exist, you need to create it by right-clicking on `HKEY_CLASSES_ROOT`, selecting `New > Key`, and naming it `prj_auto_file`.
   - Within `prj_auto_file`, create a new key named `shell` if it doesn’t exist.
   - Inside `shell`, create another key named `open`.
   - Within `open`, create a final key named `command`.

2. **Set the Default Program:**
   - In the `command` key, double-click the default value and change it to:
     ```
     "C:\Program Files (x86)\HEC\HEC-RAS\6.5\Ras.exe" "%1"
     ```
   - `%1` allows the program to receive the file as an argument.

### Apply Changes and Test:
- Close the Registry Editor.
- Restart your computer to ensure the changes take effect.
- Try opening a `.prj` file to see if it opens with the correct version of HEC-RAS.

### Note:
This is a sensitive process, as incorrect changes to the registry can cause applications or the system to behave unexpectedly. If you're not comfortable doing this, it might be wise to consult with an IT professional or someone familiar with Windows system administration.
