A simple user script that automatically hides the progress bar and icons in YouTube videos and reveals them once you hover your mouse where they would be (similar to the "Automatically Hide Taskbar" feature in Windows).

I made this script because I was annoyed that the progress bar would always block a part of the video while it's paused, and sometimes take an awkwardly long time to disappear when the video is unpaused.

If you want this script to override YouTube's own auto-hide system while the video is playing (as opposed to only while it's paused), you'll need to set the variable onlyOnPause to false in line 16 of the code. This is also documented in the code itself.

# How to install
[This script is also available on greasyfork](https://greasyfork.org/en/scripts/548136-youtube-auto-hide-progress-bar)

To use this script, you will need a userscript manager such as [Violentmonkey](https://violentmonkey.github.io/) or [Tampermonkey](https://www.tampermonkey.net/). These extensions are also available directly in the extension store for most browsers. Any other userscript extension will also work.

If you have a supported userscript manager installed, you can now easily [set up this script automatically using Greasy Fork.](https://greasyfork.org/en/scripts/548136-youtube-auto-hide-progress-bar)

**Alternatively, you can also install this script manually using the following steps:**

Open the userscript manager extension's menu and create a new script. This should redirect you to the extensions editor with a userscript template.

Click on the "userscript" file in this repository to see the code. Select all the code and copy it. Replace the contents of the userscript template with the code you just copied and save it.

The userscript is now installed and can be toggled using your userscript manager extension.

# How it works
The script is really simple:

First, it sets the opacity of the video player elements (progress bar and buttons) to 0, disables their pointer events and creates an invisible div at the bottom of the video where these elements would be.

If the mouse hovers over the div, the script resets the opacity of the elements back to 1 and enables their pointer events. It will also move the div above the progress bar.

Now, if the mouse hovers over the div again, it means that the mouse is no longer near the video player elements - the elements will be hidden again and the div moves back to the bottom of the video.
