# Field Descriptions

## UiPath Assistant

| Field | Descriptions |
| --- | --- |
| **Search** | Find available automations or reminders. |
| **Recent** | Displays the list of the last 3 run automations. |
| **Automations** | Displays the list of automations available to the user.  Note: When an automation is selected, it stays highlighted in the list. |
| **Run** | Starts the corresponding automation. |
| **Pause** | Pauses the corresponding automation.  This button is displayed only when an automation is already running.  It can be disabled for an automation from Studio. |
| **Stop** | Tries to cancel the corresponding automation, and if it does not succeed, it terminates it.  This button is displayed only when an automation is already running. |
| **Refresh** | Refreshes the list of available automations. |
| **Preferences** - The icon represents the logged in user's credentials. | Opens the **Preferences** menu. It can also be accessed by right-clicking the Robot tray icon. The following functionalities are available:   * **Preferences** - opens the **Assistant Settings** window, so that you can configure global keyboard shortcuts to pause/resume and stop automations, set the language, change   the theme and configure how the automations are displayed. * **Help** - opens the Robot Documentation Guide. * **Sign Out** or **Sign In** - sends the command to connect or disconnect the robot from Orchestrator. * **Quit** - closes UiPath Assistant. |
| **Robot** | The place where you can name and choose an image for your Robot. |
| **Launchpad** | The place where you can arrange your favorite automations individually or in groups. |

## The Assistant Settings Window

### The General Tab

| Field | Description |
| --- | --- |
| **Theme** | Enables you to change the theme for UiPath Assistant. |
| **Language** | Enables you to change the interface language of UiPath Assistant and Studio. |
| **Zoom** | Allows you to increase or decrease the size of the content in the UiPath Assistant. |
| **Automations** | **Group by folder** - this toggle organizes the automations in groups (Orchestrator folders or Widgets) on the home page.  **Note:** this option is not available for offline users.  **Show in Windows Start Menu** - enable this to make the automations available in the UiPath Assistant available in the Windows Start Menu. Enable this option to make the automations available in the UiPath Assistant accessible from the Windows Start Menu.  **Show the running tab after an automation starts** - When enabled, the Assistant focuses on the running tab when an automation starts. |
| **System** | **Automatically start Assistant with Windows** - If checked, the Assistant will start at startup, in tray mode. A similar option exists for Assistant on MacOS.  This setting is ignored when the "Automatically Start Assistant with Windows" option in the MSI installer is enabled during setup. |
| **EDR protection** | The Crowdstrike EDR (Endpoint Detection Response) protection status of your robot machines is visible in this window. You can control the visibility of this message from the Automation Ops policies, by choosing the 22.10.0 or later policy template, or by adding this information in the policies.json file. |
| **Log Level** | The level at which the Robot should log information. The following levels are available: Verbose, Trace, Information, Warning, Error, Critical, and Off. You can control if the users can change the log level from UiPath Assistant from Automation Ops. |

### The Keyboard Shortcuts Window

| Field | Description |
| --- | --- |
| **Automation Name** | An available automation for which you can set a keyboard shortcut to start it. |
| **Add Shortcut** | Allows you to configure a global keyboard shortcut to start the corresponding automation. |
| **Pause/Resume** | Allows you to configure a global keyboard shortcut which pauses or resumes the execution of the currently running automation. |
| **Stop** | Allows you to configure a global keyboard shortcut which stops the currently running automation. |

Note: In order to prevent stop/pause/resume actions that can affect multiple jobs at once, the keyboard shortcuts do not apply
to background jobs.

There are a few things to consider when you configure automations keyboard shortcuts:

* You can use up to three different modifier keys (Ctrl, Alt, Shift) and any other keyboard button. Examples: Ctrl + Alt + Shift
  + P, Ctrl + Alt + P, Shift + P. Please note that the FN key modifier is not supported.
* Your character combination can contain numpad buttons, such as Ctrl + Alt + Num3. Note that using the numerical equivalent
  instead of the assigned numpad button doesn't work.
* If your character combination contains a numerical value, its numpad equivalent does not work. For instance, using Ctrl +
  Alt + Num3 instead of Ctrl + Alt + 3.
* You can use function key from F1 to F11. Please note that F12 is not supported because it is a Windows global keyboard shortcut.
* You can not use a global keyboard shortcut which is already in use by a different application.
* If a third-party running application uses the same keyboard shortcut but is not global, the Robot keyboard shortcut is taken
  into consideration.
* Global keyboard shortcuts can be registered and used by Robots installed on virtual environments.
* If the same keyboard shortcut is used by the **Unblock options** the **Block User Input** activity and the Robot, it unblocks the user input when first pressed, and either pauses/resumes, or stops the automation
  the next time it is pressed.
* You first need to start an automation before you can use the assigned global keyboard shortcuts.

You can also zoom in using the following keyboard shortcuts:

* `Ctrl + Shift +` = to zoom in
* `Ctrl + -` to zoom out
* `Ctrl + 0` to reset

### The Orchestrator Settings Window

| Field | Descriptions |
| --- | --- |
| **Connection Type** | The connection type to Orchestrator has three options: Service URL (for Interactive Sign In), Client ID, or Machine Key. |
| **Machine Name** | The name of the machine on which the Robot is installed. It is automatically filled in. It needs to be between 1 and 15 characters. If the machine name is longer than 16 characters, then it appears truncated in the Orchestrator Settings window. For example, if your machine name is `WORKSTATIONWIN7_01` it appears as `WORKSTATIONWIN7` in the Orchestrator Settings window. The following characters are not supported:   * Backslash `\` * Slash mark `/` * Colon `:` * Asterisk `*` * Question mark `?` * Quotation mark `"` * Less than sign `<` * Greater than sign `>` * Vertical bar `|`   Please note that full stop `.` is a supported character, but the Machine Name cannot start with it. Some computer names are reserved by default. You can find out more about NetBIOS computer names and limitations on [this page](https://support.microsoft.com/en-us/help/909264/naming-conventions-in-active-directory-for-computers-domains-sites-and). |
| **Service URL** | The URL used to connect to Orchestrator when Interactive Sign In is used. Clicking the  button opens a browser window with the Orchestrator instance. |
| **Orchestrator URL** | The URL of your Orchestrator instance, such as `https://platform.uipath.com/`. The URL is saved in a drop-down menu so that next time you connect to Orchestrator you only need to select the target URL. |
| **Machine Key** | The Machine key copied from the **Provision Robot** window in Orchestrator. The key is saved. Next time you select the Orchestrator URL to connect to this field is automatically filled in with the corresponding key. |
| **Client ID** | The client ID refers to the robot identifier part of the client ID - client secret pair. This is generated in Orchestrator as described [here](/orchestrator/standalone/2023.10/user-guide/robot-authentication-with-client-credentials). |
| **Client Secret** | The client secret refers to the authorization part of the client ID - client secret pair. This is generated in Orchestrator as described [here](/orchestrator/standalone/2023.10/user-guide/robot-authentication-with-client-credentials). |
| **Sign In** | Initiates the authentication automation when Interactive Sign In is used. |
| **Sign Out** | Logs you out from Orchestrator and disconnects the Robot. |
| **Connect** | Enables you to connect the Robot to Orchestrator. This button is not available if the Robot is already connected to Orchestrator or if all the required fields are not filled in properly. |
| **Disconnect** | Enables you to disconnect the Robot from Orchestrator. This button is available only if the Robot is connected to Orchestrator. |
| **Status** | Informs you about the Robot's connection to Orchestrator. |
| **Use Assistant in Offline mode** | Use this toggle to use UiPath Assistant in Offline mode. |
| **Close** | Closes the **Orchestrator Settings** window. |

### The Launchpad Window

Here you can choose to show or hide the [Task Capture Launcher](/assistant/standalone/2023.10/user-guide/task-capture-launcher) and the ability to [submit an idea to Automation Hub](/assistant/standalone/2023.10/user-guide/automation-store-widget).

### The Tools Window

Using the **Migrate** feature, automations that are only available on your machine can be published to your Personal Workspace folder in Orchestrator.
This feature works by making a comparison between the local feed on the robot machine and the Personal Workspace folder in
the Orchestrator to which you are connected.

When an automation is migrated to your Personal Workspace for the first time, a new folder is automatically created in the
local feed location. This folder is later used to store all future automations that are migrated from the local feed to Orchestrator.

### The Help Window

This section provides you a quick access to the documentation, and a quick feedback survey.

You can also launch one of the guided tours of Assistant, or the [UiPath Diagnostic Tool](/studio/standalone/2023.10/user-guide/diagnostic-tool).

Here you can also find information about the company policy deployed, and the UiPath Assistant and Operating System version.

## Notification Menu

The notification menu in UiPath Assistant provides information about any process that needs configuration, specific details
on the tasks assigned or other details that might interest you.