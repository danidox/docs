# PiP - Virtual Desktop

**Picture in Picture - Virtual Desktop** allows you to run automations in a virtual desktop on your machine, freeing your main desktop. It also supports multiple
PiP user sessions per machine and does not require re-authentication or starting any apps already opened in the main desktop.

## How it works

When a process is started in PiP, a new virtual desktop is launched and the process runs there, leaving the main desktops
free to interact with. While the automation is running, you can see what the robot is doing and can use the **Switch to PiP desktop** button to access the virtual desktop where the automation is running.

## Controls

The following controls are available for the PiP window:

* ![docs image](https://documentationpicturerepo.blob.core.windows.net/screenshots/screenshots/keep_on_top_pip.png) - Enable this to keep the PiP window on top of other applications even when it's out of focus.
* ![docs image](https://documentationpicturerepo.blob.core.windows.net/screenshots/screenshots/min.png) Minimize - Minimizes the PiP window to the main desktop taskbar without interrupting the process.
* ![docs image](https://documentationpicturerepo.blob.core.windows.net/screenshots/screenshots/close.png) Close - Closes the PiP window.
* ![docs image](https://documentationpicturerepo.blob.core.windows.net/screenshots/screenshots/23.10%20assistant/switch_pip_desktop.png) - Enters the virtual desktop in which the PiP process is running. This allows you to interact with the automation or take
  control if needed.

## Additional information

* UIAutomation Activities v22.4 and above is required for Edge/Chrome browser automation when using PiP - Virtual Desktop.