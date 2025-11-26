# BREAKING Update
To clean things up a bit I've moved the exe whitelist out to a text file that is created next to the script.
If you were using the old version you will need to migrate your existing list manually using the examples provided.

## New feature: Add/remove programs via the script window
Use the a or r keys at any time to add or remove programs from the whitelist.

Adding programs is now super easy. Start the program, then press the a key in the script window and it should be index 0 since it sorts by the most recent process start.

# Automatic-Windows-HDR-Colour-Profile-Switcher

A powershell script for automatically swapping windows advanced colour profiles based on a whitelist of exe files. This will remove other colour profiles from the list within display settings so I suggest making sure any existing colour profiles are in "C:\Windows\System32\spool\drivers\color" so that you can easily re-add them in the colour management control panel.

This script requires administrator privileges so you will first need to create a shortcut to the script (drag and drop while holding control + shift). Then in the target field within properties, add “powershell.exe -f ” without the quotes, before the existing file path to the script. Then click the advanced button and check run as administrator.

Several things within the script also must be configured in order to work properly. Please see the script file for commented instructions.


If you want the script to auto-run on startup you can achieve this with a task in the task scheduler set to run "run with highest privelages" and start a batch file with:

```powershell.exe -windowstyle minimized -file "file path to script\Auto HDR Colour Profile Switcher.ps1"```


The script works by overwriting the registry value that stores the list of valid advanced colour profiles for a given monitor then applying the change via a built-in windows task in the task scheduler.


If anyone has the knowhow to make this more user friendly then please do. I do not have the experience required and it would take me weeks to make a GUI of some kind.

