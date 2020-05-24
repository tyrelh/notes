# Open directory in editor from dock in OSX
On OSX Mavericks:

Create your shell script.

Make your shell script executable:
```bash
chmod +x your-shell-script.sh
```
Rename your script to have a .app suffix:
```bash
mv your-shell-script.sh your-shell-script.app
```
Drag the script to the OSX dock.

Rename your script back to a .sh suffix:
```bash
mv your-shell-script.app your-shell-script.sh
```
Right-click the file in Finder, and click the "Get Info" option. At the bottom of the window, set the shell script to open with the terminal. Now when you click on the script in the dock, A terminal window will pop up and execute your script.

Bonus: To get the terminal to close when your script has completed, add exit 0 to the end and change the terminal settings to "close the shell if exited cleanly" like it says to do in this SO answer.