Show-or-Hide-Desktop-Icons
============================

**OS Compatibility:**

**Show or Hide Desktop Icons.app** has been tested and verified to run on the following versions of macOS:

**10.12 DP 1**

**Show or Hide Desktop Icons.app** has been tested and verified to run on the following versions of OS X:

**10.11.x**

**10.10.x**


Not tested on the following versions of OS X::

**10.9.x or earlier**

============================

***Using Show or Hide Desktop Icons.app***


1. If needed, download the **Show_and_Hide_Desktop_Icons** zip file from the installer directory in my GitHub repo.

2. Once downloaded and installed, double-click on the **Show or Hide Desktop Icons** application in **/Applications**.

3. Depending on if your icons are visible or hidden, the following actions take place:

**Visible icons:**

1. The `defaults` command to hide the icons is applied.
2. The Finder process is restarted.
3. A dialog window notifies you that the desktop icons are now hidden.


**Hidden icons:**

1. The `defaults` command to make the icons visible is applied.
2. The Finder process is restarted.
3. A dialog window notifies you that the desktop icons are now visible.


***How Show or Hide Desktop Icons.app works***


**Show or Hide Desktop Icons.app** is an Automator application that uses shell scripting behind the scenes to run the needed commands. When the application is launched, the following process takes place:

The script inside the Automator application determines if the desktop icons are set to be hidden or visible by checking for the following conditions:

**Condition:**

The **CreateDesktop** value in the user's **~/Library/Preferences/com.apple.finder.plist** file is either not explicitly set, or set with a boolean value of **true**.

**Action:** 

1. The `defaults` command to hide the icons is applied.
2. The Finder process is restarted.
3. A dialog window notifies you that the desktop icons are now hidden.
4. The script exits.

**Condition:** 

The **CreateDesktop** value in the user's **~/Library/Preferences/com.apple.finder.plist** file is set with a boolean value of **false**.

**Action:**

1. The `defaults` command to make the icons visible is applied.
2. The Finder process is restarted.
3. A dialog window notifies you that the desktop icons are now visible.
4. The script exits.


Blog post: [https://derflounder.wordpress.com/2016/06/26/showing-and-hiding-all-desktop-icons-via-the-command-line/](https://derflounder.wordpress.com/2016/06/26/showing-and-hiding-all-desktop-icons-via-the-command-line/)
