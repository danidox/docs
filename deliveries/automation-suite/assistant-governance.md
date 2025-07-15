# Assistant Governance

You can use UiPath® Automation Ops to govern UiPath® Assistant. Automation Ops allows you to manage and implement governance policies based on user profiles. Governance policies
offer control over various functionalities, and make sure that the rules are followed.

## Create and configure a governance policy

You can create and deploy policies per tenant for each type of license, per group, or per user. You must configure the policy
details and the product settings for each policy you create or edit.

## Assistant governance via Automation Ops (both in Cloud and Automation Suite)

The policy you create for the UiPath® Assistant allows you to:

* Choose if you allow users to install their own custom widgets.
* Choose if you want to use the UiPath® Official widget feeds. If you choose *Yes*, the widgets will be downloaded from either the official feed or your Orchestrator libraries feed. If you choose *No*, then only the Orchestrator library feeds will be enabled.
* List the widgets that you want your users to have access to by simply adding the name and the version of the NuGet package.

  Note: When switching the tenant from UiPath® Assistant, the Automation Ops policy from the new tenant applies.

## The Widgets Tab

Widgets are plugins that add functionality to the Assistant. The Widgets tab enables you to control user access to widgets.

Some widgets are added by default. On the Widgets tab, you can choose the widgets you want to deploy to your users.

Note: If you set the governance policy to not allow custom widgets, users are not able to add custom widgets, and are only able
to install widgets if they are deployed via Orchestrator or from official feeds. Additionally, if you choose to not allow
both custom widgets and official feeds, users only have access to widgets published in the Orchestrator feed.

## The Feature Toggles tab

To further configure the Assistant, from the **Governance** tab, select a policy, navigate to the **Feature Toggles** tab and choose your setup:

* **Enable Task Capture** - Select **Yes** to show the Task Capture Launcher.
* **Group processes by folders** - Select **Yes** to group processes by Orchestrator folder on the home page. To allow users to change this option from Assistant, select the
  corresponding checkbox.
* **Minimize Assistant while a process is running** - Select **Yes** to minimize the Assistant window when processes are running.
* **Automatically launch Assistant at startup** - Select **Yes** to start the Assistant at sign in time and add the Assistant icon in the Windows notification area.
* **Allow users to change the logging level in Assistant** - Select **Yes** to enable the Log Level picker in Assistant.
* **Allow users to run automations outside Personal Workspace** - Select **Yes** to allow running automations from other Orchestrator folders.
* **Enable Action Center** - Select **Yes** to allow the use of the Action Center widget.
* **Allow users to share an automation URL** - Select **Yes** to allow users to share the URL of an automation installed in a shared folder.
* **Display EDR Protection status in Assistant** - Select **Yes** to display in Assistant whether your machine is protected with EDR.
* **Allow Studio Web** - Select **Yes** to allow users to launch Studio Web from the UiPath® Products section in Assistant and return Studio Web templates in Assistant search view.
* **Switch To Running Tab** - Select **Yes** to make the Assistant focus on the running tab when an automation is launched.

## Assistant governance without Automation Ops

When UiPath® Assistant is not governed via policies set in Automation Ops, or the policy cannot be applied, the `policy.json` configuration is used. If neither of those can be used, the Assistant uses a default policy which contains the latest versions
of Marketplace and Apps Widgets.

The policy.json file contains the information related to the policies and is referenced by the agent-settings.json file.

Note: Prior to v2023.10, these settings were hosted in the `agent-settings.json` file under the `defaultNugetWidgetConfig` parameter. For v2023.10 and newer version, this parameter only references the `policy.json` file. When upgrading from a previous version of the UiPath® Assistant which contained the configuration related to the policies, the specific configuration is moved automatically into
the new `policy.json`

This can be modified by opening the `policy.json` located in `%userprofile%\AppData\Roaming\UiPath` and modifying it as follows:

Important: When setting up the policy in `policy.json`, make sure to also configure the expiration date. Otherwise, if an Automation Ops policy exists, it takes precedence until
it expires.

assignment

```
"widgets": {
        "UiPath.Marketplace.Widget": "internal",
        "UiPath.Apps.Widget": "internal"
    },
    "enableOldWidgets": true,
    "enableFallbackFeed": true,
    "expires": "2100-01-01T00:00:00.000Z",
    "policy": "My custom default policy",
    "allowTaskCapture": true,
    "enableGroupByFolder": false,
    "setGroupByFolderLocally": true,
    "launchAtStartup": false,
    "setLaunchAtStartupLocally": true,
    "minimizeWhileRunning": false,
    "onlyUiPathContentInMarketplace": false,
    "actionCenterUrl": "",
    "allowActionCenter": true,
    "allowLoggingChanges": true,
    "allowAutomationsOutsidePw": true,
    "switchToRunningTab": true,
    "allowStudioWeb": true"widgets": {
        "UiPath.Marketplace.Widget": "internal",
        "UiPath.Apps.Widget": "internal"
    },
    "enableOldWidgets": true,
    "enableFallbackFeed": true,
    "expires": "2100-01-01T00:00:00.000Z",
    "policy": "My custom default policy",
    "allowTaskCapture": true,
    "enableGroupByFolder": false,
    "setGroupByFolderLocally": true,
    "launchAtStartup": false,
    "setLaunchAtStartupLocally": true,
    "minimizeWhileRunning": false,
    "onlyUiPathContentInMarketplace": false,
    "actionCenterUrl": "",
    "allowActionCenter": true,
    "allowLoggingChanges": true,
    "allowAutomationsOutsidePw": true,
    "switchToRunningTab": true,
    "allowStudioWeb": true
```

Important:

To enable the Action Center widget in an on-premises environment without Automation Ops, you must add the following parameters
to the `policy.json` file:

* "actionCenterUrl": "https://example.com"
* "allowActionCenter": true.

To find the Action Center URL, go to the Action Center widget.

To enable the EDR protection status message from **Assistant** > **Preferences** > **General** tab, you must add the following parameters to the `policy.json` file:

* "displayEdrMessage": true