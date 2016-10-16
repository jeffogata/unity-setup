# unity-setup
Notes and files needed to fix the Unity 5.4.2f1 Setup on Windows

These notes are for Unity 5.4.2f1 on Windows 10, but I expect they apply to other versions of Windows as well.

After installing version 5.4.2f1 of Unity, I was unable to launch the Unity editor.  I would see the splash screen and then only a blank screen with a dark grey background.  It turns out there were 2 problems:

* Unity cannot be installed on a path with spaces.  Installing to the default path in `Program Files` will not work.  You will need to install to a path like `C:\Unity`.
* Unity cannot install node packages the editor needs.  You will need to manually extract and copy in the files as shown in this forum post:  https://forum.unity3d.com/threads/unity3d-5-3-not-working.372682/page-3#post-2821959.  I've included the files needed in this repo so you can simply copy the `node_modules` folder in this repo into the `Packages` folder on this path for your user account:  `C:\Users\{user-name}\AppData\Roaming\Unity\Packages\`

Note:  AppData is a hidden folder so you'll need to configure Windows Explorer to show hidden folders, or run `%AppData%` to bring up the folder (from the Start menu, type `%AppData%` or use `Windows Key + R` to bring up the Run dialog).

This looks like a regression since the 5.4.1 installer worked fine and didn't have either of the problems above.  Hopefully this get fixed soon because it's a pain to diagnose and resolve.
