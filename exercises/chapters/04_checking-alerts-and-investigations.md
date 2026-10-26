# Checking Alerts and Creating Investigations

You will now look at alerts in *SAP Enterprise Threat Detection, public
cloud* and create an Investigation object out of it.

Return to the *SAP Enterprise Threat Detection, public cloud* Monitoring
Console. If necessary, log on again with your user for ETD, and in the
Select Tenant app, select the tenant "Workshop Demo Customer".

If you receive the 'Select a Tenant' popup, refer to section
[1.1](02_logon-to-monitoring-console.md#got-a-warning-select-a-tenant) how to resolve.

## Check for Log Events

- Choose the app "Analyze Log Events" to check that your activities have
  generated log entries. Filter for your Admin user FALSEADM##. If there
  are too many entries, additionally filter for semantic Events about
  "user" or "user admin" and you should see a shorter list.

![](../media/image38.png)

- Note how the "user" column refers to the FALSEADM## user as "acting",
  but there is also an entry for "Target": This is a pseudonym for your
  newly generated FALSEUSR## user. Note down this pseudonym for later
  use.

## Search for Alerts

- Choose the app "Manage Alerts". The list should be populated with
  several recent entries. If yours is not in the system yet, give a
  little time -- generation for these Alerts is triggered by a job every
  few minutes.

- Then, filter for your user FALSEADM[\##]{.mark} in the Trigger Value 1
  or 2 fields, and press "go". Mark some Alerts you find relevant (or
  all), and in the bottom right corner, click on "Create Investigation".

![](../media/image39.png)

- In the ensuing "Create Investigation" screen, maintain a description
  referring to your demo ID so you can identify the object later. For
  "Processor", please select 'Unassigned User'

- What else you enter is not of relevance in the demo flow. Of course,
  in a productive system these settings determine how the Investigation,
  if confirming a problem, will be made visible and which follow-on
  actions it triggers.

- Next, click on "Add and Show Investigation".

![](../media/image40.png)

You will then proceed to the main screen of the Investigation you have
just created, resembling this example:

![](../media/image41.png)

## Interpreting the Investigation Entries

What is the meaning of the different parts of the Investigation object?

- In the Investigation screen, you will find the header information you
  have maintained before. You can choose to "edit" in case you wish to
  change the information.

- In the middle section, you find several tabs, which can be filled with
  additional information:

### Tab 'Investigation Result'

The edit field can be filled by using the 'Generate Recommendation'
Button, which makes use of the two AI skills 'Template Generation' and
Object-Explanation.

![](../media/image42.png)

Click the Button Generate Recommendation, and the 'Investigation Result'
field gets filled with the template with placeholders replaced for each
alert added to the investigation, plus explanations on criticality for
possible objects, which were alerted (e.g. transactions, reports,
function modules, web services).

![](../media/image43.png)

The field is editable by the security analyst, i.e. he can correct/adopt
the text, re-generate it, add additional findings. Clicking the 'Save'
Button saves the text including all manual changes.

### Tab 'Alerts'

Here, you can research the Alerts added to the investigation, have a
look at some of the complete triggers explanation texts and how they
codify the core findings in this text. You may also review some of the
triggering Events.

- ![](../media/image44.png)

- In the Trigger text, you might also come across at least one
  additional user -- in the form of a "User Pseudonym, Target". Note
  down the pseudonym of this user (which you will later see refers to
  your FALSEUSR## user that was granted high level authorizations).

- In a real life scenario (but beyond the scope of a demo like this),
  user pseudonyms or other specific pointers like IP addresses, terminal
  ID/computer name etc. would be used to extend the search for alerts
  which are relevant for an investigation.

### Tab 'Actions'

> In Tab 'Actions', you find all activities, so far done as actions
> related to the current investigation. Additionally, you may document
> anything (if not wanted in the Edit-field for the 'Investigation
> Result') - actions you have been performing, preliminary findings etc.
> and deductions these allow. These insights will be rendered in the
> investigation report later.
>
> ![](../media/image45.png)

### Tab 'Users'

In the 'Users'-Tab, you can verify all mentioned User-IDs occurring in
the list of alerts, to get a better overview about involvement.
Additionally, the User-IDs can be de-pseudonymized, which makes sense,
in case there are evidences for a suspicious behaviour, or a question
about the legitimization of a user needs to be raised.

![](../media/image46.png)

### Tab 'Behavior Analysis'

This tab provides an AI based functionality to analyse critical log
events in the 'neighbourhood' of the related alerts, to find out if any
other critical activities, in the light of the related alerts, but not
related to any alert, exist. The functionality provides a list of
critical events, with explanation and reasoning about the criticality,
plus an AI based Severity Scoring. The security analyst can review the
additional findings and add them to the investigation, where they then
appear in the 'Log Events' Tab.

In the tab, click the Button 'Start Behavior Analysis'

![](../media/image47.png)

In the following UI, you decide, for which user the Analysis shall be
done, plus the time range.

![](../media/image48.png)

**Note:** As this is an 'embedded' AI feature without additional cost,
the token consumption and the maximum number of log events per analysis
is restricted.

**Note:** As a rather big amount of log data might be examined
additionally, this is an asynchronous process, which can take several
minutes, shown by the progress bar.

![](../media/image49.png)

Checkmark some of the additional log events, review them, and add them
to the investigation

![](../media/image50.png)

After adding, the number of Log Events in the 'Log Events' tab is raised

### Tab 'Log Events'

In this tab, additional log events, which are relevant for the
investigation context and added either manually (from the 'Log Events
Viewer' Tile), or semi-automatically (as suggestion from the AI from a
Behaviour Analysis).

---
Prev: [2. First Log Events from SAP S/4HANA](03_first-log-events.md) | Next: [4. Trigger a Critical Action from SAP S/4HANA](05_trigger-critical-action.md) | [Contents](../README.MD)
