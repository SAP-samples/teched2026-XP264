**Hands-on experience with SAP Enterprise Threat Detection, cloud
edition**

**Exercise: Working with SAP Enterprise Threat Detection** **Version**

**Based on SAP Enterprise Threat Detection, cloud edition, Version
October 2026**

**Get Hands-On with the New
*SAP Enterprise Threat Detection, cloud edition***

**\**

# Contents

Overview & Touring SAP Enterprise Threat Detection, public cloud
[3](#overview-touring-sap-enterprise-threat-detection-public-cloud)

1\. Logon to the Monitoring Console of SAP Enterprise Threat Detection,
public cloud
[4](#logon-to-the-monitoring-console-of-sap-enterprise-threat-detection-public-cloud)

1.1 Got a Warning 'Select a Tenant' [6](#got-a-warning-select-a-tenant)

1.2 UI Round trip [6](#ui-round-trip)

2\. First Log Events from SAP S/4HANA
[17](#first-log-events-from-sap-s4hana)

2.1 Logon & Preparation Steps [17](#logon-preparation-steps)

2.2 Creating a User With High Privileges
[18](#creating-a-user-with-high-privileges)

3\. Checking Alerts and Creating Investigations
[21](#checking-alerts-and-creating-investigations)

3.1 Check for Log Events [21](#check-for-log-events)

3.2 Search for Alerts [21](#search-for-alerts)

3.3 Interpreting the Investigation Entries
[23](#interpreting-the-investigation-entries)

3.3.1 Tab 'Investigation Result' [23](#tab-investigation-result)

3.3.2 Tab 'Alerts' [23](#tab-alerts)

3.3.3 Tab 'Actions' [24](#tab-actions)

3.3.4 Tab 'Users' [24](#tab-users)

3.3.5 Tab 'Behavior Analysis' [25](#tab-behavior-analysis)

3.3.6 Tab 'Log Events' [26](#tab-log-events)

4\. Trigger a Critical Action from SAP S/4HANA: Download of a Critical
Database Table
[26](#trigger-a-critical-action-from-sap-s4hana-download-of-a-critical-database-table)

5\. User & Environment Behavioral Analysis -- Identify the Critical
Action in the Forensic Lab
[28](#user-environment-behavioral-analysis-identify-the-critical-action-in-the-forensic-lab)

5.1 Build up a Workspace [29](#build-up-a-workspace)

5.1.1 Assigning a Chart [38](#assigning-a-chart)

6\. From Workspace to Pattern to Alerts
[39](#from-workspace-to-pattern-to-alerts)

6.1 Understanding Patterns [39](#understanding-patterns)

7\. Finalize the Investigation [42](#finalize-the-investigation)

8\. Consumer/Processor role: Work with Investigation reports
[45](#consumerprocessor-role-work-with-investigation-reports)

# Overview & Touring SAP Enterprise Threat Detection, public cloud

In this hands-on session and workshop of about 1.5 -- 2h, you will get
to know the basic functioning of *SAP Enterprise Threat Detection,
public cloud*, including the terminology employed.

You will switch back and forth between 3 roles. In a first role, you
will be a (potential) threat actor in an SAP S/4HANA system and conduct
actions resulting in system responses in *SAP Enterprise Threat
Detection, public cloud*.

In a second role, you will act as a security specialist in charge to
identify potential threats, pin down what has happened and determine the
relevance, as well as ensure that the knowledge about the attack vector
is added to the repository on which *SAP Enterprise Threat Detection,
public cloud* will automatically alert going forward.

In a 3^rd^ role, you will act as a consumer/processor of the results
(Investigation Report), that was created by you in your second role as a
security specialist.

Here's the flow of the following exercises in your roles as threat actor
and security specialist (the numbers relate to the chapters in this
document:

![](media/image1.png)

Chapters 1 to 7 are related to these to roles. Chapter 8 is related to
the consumer/processor role

# Logon to the Monitoring Console of SAP Enterprise Threat Detection, public cloud

Access the [*SAP Enterprise Threat Detection, public cloud* monitoring
console](https://etd-cloud-workshop-partner-nten9gd6-monitoringapprouter.prod.monitoring.etd-cloud.cfapps.eu10-004.hana.ondemand.com/cp.portal/site?targetTenantId=9189d8d0-c3ea-4f11-a145-1a7d13e32c3d&origin=monitoring#Shell-home)

[IMPORTANT:]{.underline}

- You should get the below start page (if not, please empty your browser
  cache and try again).

- Here, select the first entry ("httpsetdtestlogs.accounts.ondemand") to
  log on with the generic workshop users below (not any personal
  credentials -- they won't be recognized in this cloud application).
  Do **[NOT]{.underline}** choose the "Default Identity Provider" (here,
  the generic users won't work).

![](media/image2.png)

User: will be provided in the session

Password: will be provided in the session

In the ensuing (logon) screen, use the ID indicated to you ([01-40;
afterwards]{.mark} referred to as "##").

> User: Will be provided in the Session
> Password: Will be provided in the session

If you inadvertently lock the password, please notify the instructor.

If you receive a blank screen saying "Where to", please clear the cache,
then close and restart the browser. If you may also open an private
browsing window (often "incognito" or "InPrivate"). Log on again.

Upon initial logon, In case you get pop-up message to select a Tenant,
than click the Select Tenant screen for selecting a specific Tenant:

As a monitoring agent providing services to multiple clients, you will
log on to your organization's own productive Tenant; however from here
commonly access and work in the specific Tenant of a client, which you
can select from this list reflecting all clients/Tenants linked to your
organization.

For this hands-on there is only one customer system linked. Click on the
blue hyperlink and select "Workshop Demo Customer".

![](media/image3.png)

You will then see the *SAP Enterprise Threat Detection, public cloud*
monitoring console. Take a bit of time to check by a few apps and how
they behave.

![](media/image4.png)

## Got a Warning 'Select a Tenant'

If you encounter a the warning popup

![](media/image5.png)

the system has lost the information which Tenant you've been working on
(most likely you had been logged out).

In this case, either start the *SAP Enterprise Threat Detection, public
cloud* console again via the above link.

Alternatively, you can manually set the correct tenant:

- In the section for "Cross-Tenant Applications", open the app "Select
  Tenant".

- Remove filters "active" and press "go".

- The entry "Workshop Demo Customer" will show; select this so the
  system is aware which Tenant you are working on -- which is relevant
  in case you're a partner providing monitoring services to multiple
  clients)

![](media/image6.png)

![](media/image7.png)

## UI Round trip

In Manage Setting tab, users can manage system setting like retention
times and time zone etc.

![](media/image8.png)

In Value list tab, users can manage value lists which are allow or
disallow list where system analyst and put custom values and even can
create custom value lists

![](media/image9.png)

To look into the entries of a value list, click on the corresponding
value list entry.

**Note:** Some value lists are related to special object types (like
transactions, reports, function modules, services), which allow to
retrieve additional, AI supported information about the object (what is
it, why is it security relevant, how to mitigate).

![](media/image10.png)

Clicking on the 'see more' button provides this additional context
information.

![](media/image11.png)

As you know: AI can provide wrong information. Then, you can provide a
feedback to SAP via the 'Feedback' button, and SAP will centrally repair
the AI answer, to enhance quality.

In Analyze Log Events tab, the security analyst can view and analyze
customers normalized log data.

![](media/image12.png)

**Note:** If the log contains objects like transactions, reports,
function modules, services, you get an AI based support about the
object, its criticality, and possible security mitigations.

![](media/image13.png)

In Manage Alerts tab, system analyst and view and analyze generated
alerts.

![](media/image14.png)

**Note:** If the Alert attributes contain objects like transactions,
reports, function modules, services, you get an AI based support about
the object, its criticality, and possible security mitigations.

![](media/image15.png)

In Pattern Executions tab, the security analyst can view and check the
status of pattern executions

![](media/image16.png)

In Pattern tab, the security analyst can view and create patterns( i.e.
use cases) ![](media/image17.png)

Clicking on one of the patterns, the UI shows its overall modelling and
description.

![](media/image18.png)

If you scroll further down, you see the existing 'Recommendation
template', which is used for processing corresponding alerts within
investigations. During the processing, the template is used, to generate
a text by filling the placeholders.

![](media/image19.png)

The template itself is generated with AI assistance. Customers can
overwrite SAP delivered templates, by generating their own ones, and
e.g. adding their own policies. During alert processing in
investigations, not only the template is filled and added to the report,
but as well the information about the criticality of an object,
mentioned in the alert (like transactions, reports, function modules,
services). For custom patterns, a corresponding template can be
generated as well.

In Investigations tab, the security analyst can view and manage
investigations.

![](media/image20.png)

In 'Record of Actions' tab, system analyst and view use activity logs of
ETD system

![](media/image21.png)

In Investigations Report tab, the security analyst can view
investigations.

![](media/image22.png)

In the 'Forensic Lab' tile, and the Workspaces UI, the Security analyst
can view and create Workspaces, which are used to filter data related to
suspicious activities, and to create charts to group the data by any
criteria. Based on these charts, Patterns, later raising alerts, can be
created.

![](media/image23.png)

By clicking onto the arrow on the right at any line, you see the
modelling of the forensic workspace, related to filter paths and charts.
This so part of Exercise Chapter [5.1](#build-up-a-workspace).

In the Dashboard tile, different standard dashboards are shown, and own
custom dashboards can be created.

![](media/image24.png)

Within a custom dashboard, any number of charts can be added from a list
of predefined charts.

![](media/image25.png)

In the 'Manage Incoming logs' tile, the security analyst can view
incoming logs, and find out, if there are any log outages from a system
ID, or of a special log type.

![](media/image26.png)

In the 'Resolve User Identity' tile, the security analyst can
de-pseudonymize user pseudonyms. This might be needed in case there are
evidences of a suspicious activity of a user. In order to be able to
search for a activities of a user (e.g. as to external signals), the
user's pseudonym can be determined reverse, to search for it in the log
data.

![](media/image27.png)

# First Log Events from SAP S/4HANA

Please note: in this exercise, every workshop station/computer has a
designated set of users already existing; throughout the description,
"##" is the number of your workshop computer ID.

In this section, you will conduct actions in SAP GUI to generate Log
Events which in return will result in Alerts in *SAP Enterprise Threat
Detection, public cloud*.

## Logon & Preparation Steps

- access the WebGUI interface:
  <https://3.97.131.191:44301/sap/bc/gui/sap/its/webgui>

- Proceed through the "advanced" mode in case you get a warning of
  unsafe/non-private connection -- which might look like this:

![](media/image28.png)

![](media/image29.png)

Log on credentials:

User: FALSEADM##

Password: Will be provided in the session

If you inadvertently lock the password, please notify the instructor.

If you should not see the 'OK Code' field:

- Activate the display of the "transaction code entry" field for easier
  navigation:
  Go to Menu 🡪 Settings 🡪 Visualization.
  Activate "Show OK Code field" as well as "Show dropdown lists with
  keys" and "Sort dropdown lists by their keys" and save.

> ![](media/image30.png)

- Leave the menu. Your start screen should now show the transaction code
  entry field:

> ![](media/image31.png)

## Creating a User With High Privileges

You will now conduct an action which triggers your first logs into *SAP
Enterprise Threat Detection, public cloud:* creating a highly privileged
user.

- In the transaction code entry, enter "SU01" (User Maintenance), and
  hit enter.

![](media/image32.png)

- In the User Maintenance transaction start screen, enter your user
  FALSEADM## in the User field, and select "copy".

![](media/image33.png)

- In the pop up screen, maintain the new user name "FALSEUSR##" in the
  "To:" field; deselect the option to copy authorization profiles, and
  press "copy":

![](media/image34.png)

- In the resulting screen set, on tab "Logon Data", assign an initial
  (temporary) password (it is suggested to note down this password as
  you will need this to log on with FALSEUSR##). Then save the user.

![](media/image35.png)

- Back in the SU01 initial screen, put in your user FALSEUSRxx and
  select the button "Change". Move to the tab "Profiles", add the
  profile "SAP_ALL" (making this user a super user basically without
  restrictions), and hit enter. Then press "Save".

![](media/image36.png)

- This has been the first set of noteworthy actions.

- Additionally, we suggest to call some other transactions with that
  user, which are presumably not alerted, but, however, logged, and can
  be seen later, in a Behavior analysis step for that user. **E.g.**
  (i.e. not restricted to) you can call transaction SU01D, SU24, BP, or
  FI02, which is not alerted, but may be to be considered in the context
  of the raised alerts.

- Exit the SAP Web GUI (button "Exit" in the top right; or hit Shift+F3;
  or in the transaction code entry field, type "/nex").

![](media/image37.png)

# Checking Alerts and Creating Investigations

You will now look at alerts in *SAP Enterprise Threat Detection, public
cloud* and create an Investigation object out of it.

Return to the *SAP Enterprise Threat Detection, public cloud* Monitoring
Console. If necessary, log on again with your user for ETD, and in the
Select Tenant app, select the tenant "Workshop Demo Customer".

If you receive the 'Select a Tenant' popup, refer to section
[[1.1]{.underline}](#got-a-warning-select-a-tenant) how to resolve.

## Check for Log Events

- Choose the app "Analyze Log Events" to check that your activities have
  generated log entries. Filter for your Admin user FALSEADM##. If there
  are too many entries, additionally filter for semantic Events about
  "user" or "user admin" and you should see a shorter list.

![](media/image38.png)

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

![](media/image39.png)

- In the ensuing "Create Investigation" screen, maintain a description
  referring to your demo ID so you can identify the object later. For
  "Processor", please select 'Unassigned User'

- What else you enter is not of relevance in the demo flow. Of course,
  in a productive system these settings determine how the Investigation,
  if confirming a problem, will be made visible and which follow-on
  actions it triggers.

- Next, click on "Add and Show Investigation".

![](media/image40.png)

You will then proceed to the main screen of the Investigation you have
just created, resembling this example:

![](media/image41.png)

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

![](media/image42.png)

Click the Button Generate Recommendation, and the 'Investigation Result'
field gets filled with the template with placeholders replaced for each
alert added to the investigation, plus explanations on criticality for
possible objects, which were alerted (e.g. transactions, reports,
function modules, web services).

![](media/image43.png)

The field is editable by the security analyst, i.e. he can correct/adopt
the text, re-generate it, add additional findings. Clicking the 'Save'
Button saves the text including all manual changes.

### Tab 'Alerts'

Here, you can research the Alerts added to the investigation, have a
look at some of the complete triggers explanation texts and how they
codify the core findings in this text. You may also review some of the
triggering Events.

- ![](media/image44.png)

- In the Trigger text, you might also come across at least one
  additional user -- in the form of a "User Pseudonym, Target". Note
  down the pseudonym of this user (which you will later see refers to
  your FALSEUSR## user that was granted high level authorizations).

- In a real life scenario (but beyond the scope of a demo like this),
  user pseudonyms or other specific pointers like IP addresses, terminal
  ID/computer name etc. would be used to extend the search for alerts
  which are relevant for an investigation.

### Tab 'Actions'

> In Tab 'Actions, you find all activities, so far done as actions
> related to the current investigation. Additionally, you may document
> anything (if not wanted in the Edit-field for the 'Investigation
> Result') - actions you have been performing, preliminary findings etc.
> and deductions these allow. These insights will be rendered in the
> investigation report later.
>
> ![](media/image45.png)

### Tab 'Users'

In the 'Users'-Tab, you can verify all mentioned User-IDs occurring in
the list of alerts, to get a better overview about involvement.
Additionally, the User-IDs can be de-pseudonymized, which makes sense,
in case there are evidences for a suspicious behaviour, or a question
about the legitimization of a user needs to be raised.

![](media/image46.png)

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

![](media/image47.png)

In the following UI, you decide, for which user the Analysis shall be
done, plus the time range.

![](media/image48.png)

**Note:** As this is an 'embedded' AI feature without additional cost,
the token consumption and the maximum number of log events per analysis
is restricted.

**Note:** As a rather big amount of log data might be examined
additionally, this is an asynchronous process, which can take several
minutes, shown by the progress bar.

![](media/image49.png)

Checkmark some of the additional log events, review them, and add them
to the investigation

![](media/image50.png)

After adding, the number of Log Events in the 'Log Events' tab Is raised

### Tab 'Log Events'

In this tab, additional log events, which are relevant for the
investigation context and added either manually (from the 'Log Events
Viewer' Tile), or semi-automatically (as suggestion from the AI from a
Behaviour Analysis).

# Trigger a Critical Action from SAP S/4HANA: Download of a Critical Database Table

In this section, you will return into the role as a rogue actor and
conduct several more actions resulting in Log Events flowing into *SAP
Enterprise Threat Detection, public cloud*.

First, you need to log on to the SAP S/4HANA with the newly generated
user FALSEUSR##.

- In order to log on with your new user FALSEUSR##, you need to either
  **[open a new "incognito"/"private" session in your browser]{.mark}.**

Alternatively, you may also switch to another browser.
Emptying the browser cache is also an option. Here, mark at least
history, cookies, and password sections, then confirm).

- Now, call the Web Gui console
  <https://3.97.131.191:44301/sap/bc/gui/sap/its/webgui>, logon with
  your new user FALSEUSR## and the password you have chosen. At start,
  you need to set a new password (suggestion to take a note).

Executing a critical action:

- With the transaction code entry, navigate to transaction SE16N. This
  is a table display/download transaction (and a tool so powerful that
  it should generally not be made available in a productive system...).

![](media/image51.png)

- In the transaction, call table USR02. USR02 is a table which holds
  personal information (bad enough) and stores user password hashes
  (very critical: Although the passwords are hashed out, this would not
  stop a determined attacker. They may either crack simple passwords
  and, if they have identified out one single password from any user,
  they can take the respective hash value to overwrite the hashed
  password of any other user, allowing them to log on as that user i.e.
  impersonate the other user. Theoretically the password hashes should
  be "salted" however, in practice, this attack vector has been working
  quite reliably.

(That said, think about the value of MFA and other tools independent
from passwords).

- Access with the function "Online":

![](media/image52.png)

- Search for your user FALSEUSR## and display details. Check out
  Password Hash Value ( real table attribute name PWDSALTEDHASH),
  towards the end of the table.

- Return to the table display and trigger a download with the icon
  "Export", then choose "local file" and confirm the following two
  interactions. The file can be stored anywhere -- in case you need to
  indicate a directory, pick any that you like.

![](media/image53.png)

You have conducted a seemingly simple but dangerous activity which
should result in at least one Alert in *SAP Enterprise Threat Detection,
public cloud*.

Additionally, we suggest to call some other transactions with that user,
which are presumably not alerted, but, however, logged, and can be seen
later, in a Behavior analysis step for that user. **E.g.** you can call
transaction SU01D, SU24, BP, or FI02, which is not alerted, but may be
to be considered in the context of the raised alerts.

Let's continue to retrieve and process the raised alerts!

#  User & Environment Behavioral Analysis -- Identify the Critical Action in the Forensic Lab

The Forensic Lab is the area where you work on ways to identify new
potential threat vectors by filtering your way through the large volume
of log entries until you arrive at a definition yielding few and
specific logs that should point at a real threat.

Here, we will build a workspace with filters capable of identifying the
case where a user is granted high authorizations, and then accesses a
critical resource.

To this end, we will be building two filtering Paths linked by a
Reference:

- "Path 1" should be capable of establishing a list of users who have
  been granted critical authorizations in the past 2 days.

- "Path 2" to the right shall be able to establish a list of all users
  who have accessed a critical resource recently.

- The "Reference" allows to single out users which are in the result
  lists of both paths.

The Workspace will look similar like this one:

![](media/image54.png)

## Build up a Workspace

- Return to the monitoring console of SAP Enterprise Threat Detection,
  cloud edition.

- Go to the app "Forensic Lab".

> ![](media/image55.png)

- In the area "Custom Workspaces", you see a list of existing
  workspaces.

- Create a new Workspace with Name ##TechEdPWHashAttack, by replacing
  the \## with your participant number. Enter some additional
  information (Use case, Severity, Description), and then click on
  'Create'

> ![](media/image56.png)

- Then the your new Workspace arrives in the Workspace list, and is
  opened automatically to continue working. To open it later, you can
  click on the name link in the list, or on the arrow on the right for
  your Workspace.

![](media/image57.png)

- Your new workspace contains already a first Filter Path (Path 1) with
  a subset (Subset 0) to filter on the time range.

- Click on the 'Refresh' Button
  ![](media/image58.png)to see incoming log data.

- Click into the Subset 0, to get some Symbols at the right

- Click into the Pi-Chart Symbol to view the data in a chart preview.
  You see as a default the distribution of log events, related to their
  systems

- By clicking on the Drop-Down-Symbol, you can select other attributes
  of the ETD normalized Data Model

> ![](media/image59.png)
>
> By e.g. selecting 'Event (Semantic)' you get a distribution of all log
> events, related to the Semantic Events.
>
> ![](media/image60.png)

- By clicking the 'Edit' Button
  ![](media/image61.png),
  you start modelling your workspace. You see now some additional
  Symbols at the right of your Subset 0.

- Change the relative Timestamp of Subset 0 to 2 hours by clicking on
  the symbol 'Edit Subset'
  ![](media/image62.png)

> ![](media/image63.png)
>
> ![](media/image64.png)
>
> ![](media/image65.png)
>
> ![](media/image66.png)

**Information:** [To be able to see some data in the following filter
steps, directly before the session started, all FALSEADM## users in the
S4/H system got a mass change by adding a high privilege.]{.mark}

- By clicking on the 'Create Subset'
  ![](media/image67.png) Symbol, a Popup appears to enter the
  filter criteria for the next subset. Please enter:

  - Semantic Attribute: Event (Semantic)

  - Type: Value

  - Operator: Equal

  - Value: User Admin, Privilege, Grant

- Then click 'Apply'.

- ![](media/image68.png)

- Your new Filter Subset 'Subset 1' appears. By clicking into the Subset
  1, you can use the small symbols at the side (especially the Pie-Chart
  Symbol) to do a preview on the data filtered in Subset 1 in the
  Preview area.

- Sometimes click on the 'Save' Button

> ![](media/image69.png)

- Create a new Subset
  ![](media/image67.png) to filter (for Demo Purposes) on your
  own ABAP User FALSEADM\<YourNumber\>. In the Popup enter:

  - Semantic Attribute: User Pseudonym, Target

  - Type: Value

  - Operator: Equal

  - Value: FALSEADM\<YourNumber\>

- Then click on 'Create'

> ![](media/image70.png)

- You new Subset is showing as 'Subset 2'. By refreshing and selecting
  the Pie Chart you can see some data in Subset 2.

**Information**: ETD provides a role concept about users, systems, IP
addresses, etc. An 'Acting User' is a user, who does something. A
'Target User' is e.g. a user, to whom something is done.

- Create a new Subset with the following values:

  - Semantic Attribute: Privilege Name

  - Type: Value

  - Operator: In value list

  - Value: AuthorizationCriticalAssignmentProfiles

- Then click on 'Create'

![](media/image71.png)

- You new Subset is showing as 'Subset 3'. By refreshing and selecting
  the Pie Chart you can see some data in Subset 3.

**Information**: The value list AuthorizationCriticalAssignmentProfiles
contains typical predelivered values for Profiles (e.g. SAP_ALL,
SAP_NEW, ...). The filter is then set as an 'IN'-filter about all
values.

To be able to corelate the provisioning of a high privilege with the
miss-use of the privilege (in the example: look up Password hashes), a
second filter path needs to filter on that activity, and then corelate
to the high privilege provisioning (via reference filter).

- Click the 'Create Path' Symbol

![](media/image72.png)

- Select the Context 'Log' and 'save'. Your second filter path 'Path 2'
  is created and already contains a timestamp filter in Subset 0.

- Again, change the timestamp filter to Last 2 hours (to be able to see
  some data). Then you can click the 'Refresh' symbol and the
  'Pie-Chart' symbol to see the data of Path2, Subset 0.

> ![](media/image73.png)

- Create a new Subset with the following values:

  - Semantic Attribute: Service, Transaction Name

  - Type: Value

  - Operator: In

  - Value: SE16, SE16N, SE11

    i.  **[Hint]{.underline}**: To enter the In-Value List, enter the
        1^st^ value, then press 'Enter', then enter the 2^nd^/next value
        and always press 'Enter' in between. The single values are shown
        separately.

- Then click on 'Create'

> ![](media/image74.png)

- Your new Subset is showing as 'Subset 1' in Path 2. By refreshing and
  selecting the Pie Chart you can see some data in Subset 1.

- Create a new Subset with the following values:

  - Semantic Attribute: Event (Semantic)

  - Type: Value

  - Operator: In

  - Value: Data, Download ; Database, Data, Select, Generic

    i.  **[Hint]{.underline}**: To enter the In-Value List, enter the
        1^st^ value, then press 'Enter', then enter the 2^nd^/next value
        and always press 'Enter' in between. The single values are shown
        separately. You can as well check if the Semantic events are
        visible in the selection box, then you can select them via
        checkboxes

- Then click on 'Create'

> ![](media/image75.png)

- Your new Subset is showing as 'Subset 2' in Path 2. By refreshing and
  selecting the Pie Chart you can see some data in Subset 2.

- Create a new Subset with the following values:

  - Semantic Attribute: Resource Name

  - Type: Value

  - Operator: In value list

  - Value: CriticalDatabaseTables

    i.  Hint: The Attribute 'Resource Name' contains objects (like DB
        tables, files) from where/to which data is read/written

- Then click on 'Create'

> ![](media/image76.png)

- Your new Subset is showing as 'Subset 3' in Path 2. By refreshing and
  selecting the Pie Chart you can see some data in Subset 3.

- Finally, create a Subset, which corelates between Path 1 filter
  results for provisioning of high privileges to a **target** user, and
  path 2 results for the same **acting** user accessing a critical DB
  table with Password hashes. Use the following values:

  - Semantic Attribute: User Pseudonym, Acting

  - Type: Reference

  - Operator: In

  - Reference To: Subset 3, Path 1

  - Value: User Pseudonym, Target

- Then click on 'Create'

![](media/image77.png)

- Your new Subset is showing as 'Subset 4' in Path 2. By refreshing and
  selecting the Pie Chart you can see some data in Subset 4. Data can be
  seen if within last 2 hours the user got a high privilege,
  [and]{.underline} in the same timeframe accessed a critical DB table.

The final result should look like this:

![](media/image54.png)

### Assigning a Chart 

The Workspace and filters you have built defines a way to identify
events pointing at a new threat. In real life, if you suspect this is an
attack and that it might repeat, you want to re-use these definitions
and actually automate them to throw an Alert whenever the same
occurrence happens again.

To this end, the logical next step in *SAP Enterprise Threat Detection,
cloud edition* is to define (name and save) the Browsing Chart
pertaining to one of your Subsets.

Such a named Chart can then be used to build a new Pattern -- which
generates Alerts whenever Log Entries pertaining to the Subset/Chart
reach a predefined threshold (e.g. "more than 5 processed bank account
numbers per day", or "every single access to a critical database
table").

This is the primary way of building new content in *SAP Enterprise
Threat Detection, public cloud*.

In this demo case, we look to the final Subset on "User Pseudonym,
Acting" in Path 2. Switch to edit mode again, and mark Subset 4, Path 2.
Then press "Create Chart":

![](media/image78.png)

In the pop-up, assign a name among the lines of
"\<YourNumber\>PWHashAttack", and a description. Mark down the name.

For measurement, choose the "count" \* and a fitting Display Name if you
like:

![](media/image79.png)

Click on "Create". In the ensuing screen, choose to "Group By" the
semantic events

- Resource Name

- Service, Transaction Name

- System ID, Actor

- User Pseudonym, Acting

The resulting Chart should be looking something like this. Note how the
grouping results in the resource USR02 and a user pseudonym being
displayed (which should be the pseudonym assigned to your FALSEUSR##
user):

![](media/image80.png)

- [Finally, click the 'Save' Button]{.mark}

> Note: Per each deviating combination of the (in this example) 4
> grouped attributes, there would arrive another bar in the bar chart.

# From Workspace to Pattern to Alerts

## Understanding Patterns

- Return to the Console Home Screen and Enter the "Manage Patterns" app.

- Choose to "Create Pattern" and in the pop-up maintain the relevant
  information. Importantly, set the status to "Active", frequency to the
  lower limit of 5 minutes; and Threshold to \>=1. In the "Chart" field,
  retrieve and assign the Chart you have created.

![](media/image81.png)

The fields for Success of Attack and Credibility of Attack Detection can
help to gauge the severity of a breach, but does not have a direct
influence in the context of this hands-on session.

**Information:** If you mark the checkbox 'Test Mode', then alerts will
as well be created, and be visible in the alert list, but they will be
in status 'Test Mode' and can be deleted later-on. Reasoning is, that in
'Test Mode', the Pattern is still reworked, until it functions properly,
and does not create too many false positives. Later, the marker can be
removed, and from that time on, the alerts cannot be deleted any more,
as they are now seen as real alerts, and deletion might cause compliance
issues.

Save your work.

Scroll the UI down to the Area 'Recommendation Template'.

![](media/image82.png)

As it is a custom Pattern, there is no predefined SAP template,
delivered for standard content.

Now, you create a Recommendation Template for your own Pattern, to use
it later in the Investigation handling when clicking on 'Generate
Recommendation'. Click the 'Edit Button' again, click on tab 'Custom
Template', then click on button 'Create'.

![](media/image83.png)

Into chat field, enter a small ask, like 'Create a SOP'. (SOP stands for
Standard Operation Procedure). **Note:** As the AI cannot find out the
content about generic attributes (like 'Parameter Name', Parameter
Value, String, ..), you can as well provide hints (Like: 'Information:
Parameter Value contains the Business Partner ID') to be recognized in
the recommendation text.

Then press the button to start the generation.

![](media/image84.png)

After the generation is finished, you see the generated text, and the
Query Parameters, which are located in the text as placeholder in
brackets (e.g. \[{{AlertDetails.ServiceTransactionName}}\] ). You
additionally can edit and correct the template text directly in the
editor, or you can ask in the chat window to add a sentence, etc.)

**Note:** You can add additional data from the triggering events, not
only from the grouping attributes of the alert. If you want to enrich
the template text maybe with the IP address used, but not grouped in the
Chart from the Forensic Workspace, you can ask the AI to add the
attribute (e.g. 'Add the 'IP Address Initiator additionally' from the
triggering events into the Investigation result.

The result you see, looks like:

![](media/image85.png)

**Note:** On the right side, you can as well mark some attributes as so
called 'Fixed Dimensions' The result is, that several Alerts within an
investigation, related to the same Pattern, are aggregated in one text
around the fixed dimension. Example: If you have a user that called 5
different critical transactions, you get 5 alerts. If you want to have a
generated text like: 'The user called transaction A, B, C in system
XYZ', then you mark the user as a fixed dimension. If you do not mark,
you 5 similar texts, for just each of the 5 alerts. Very typical is to
mark the User Acting and the System ID Actor (if the attributes are
filled and available).

![](media/image86.png)

Click the 'Save Button'. Your Pattern is finished.

Finally, in the resulting screen, trigger the button "Execute" to run
the pattern on the logs in the hot storage (evaluating past logs for the
event happening), and generate Alerts.

![](media/image87.png)

- Finally, return to the Manage Alerts app. Filter for Alert(s)
  pertaining to your pattern xx_PWHashAttack. Have a look at the
  "trigger" field, detailing the resource and the user (pseudonym)
  responsible for creating the alert (if necessary, expand the
  text/field).

Your Alert looks like:

![](media/image88.png)

- Mark the alert(s), and add them to your Investigation, by filtering
  the alerts related to the user pseudonym (Acting) in your alert
  created by your own pattern.:

![](media/image89.png)

In the following screen, press "Add and Show Investigation":

![](media/image90.png)

# Finalize the Investigation

You can now conclude the Investigation.

- In the app for "Manage Investigations", you will find the header
  information you have maintained before and can edit. You may choose
  "edit" in case you desire to change the information.

- In the middle section, click on "Alerts". Here, you can research the
  Alerts, have a look at some of the complete triggers explanation texts
  and how they codify the core findings in this text. You may also
  review some of the triggering Events.

![](media/image91.png)

- In the Trigger text, you may also come across additional user
  pseudonyms or references to IP addresses from where the triggering
  actions were initiated. These can be valuable leads to follow up on --
  If you have time left, you may note down the pseudonyms (or also users
  in clear) and IP addresses, return to the Manage Alerts app, search
  for more Alerts involving these pseudonyms, and add the results to
  your Investigation.

![](media/image92.png)

- Finally, return to your Investigation. You may comment/document what
  actions you have been performing, and what deductions these allow.

- Then return to the tab for "Users". For each pseudonym, trigger the
  de-pseudonymization:

![](media/image93.png)

- This will reflect in the "Actions" tab -- have a look at the clear
  user names. You should be spotting your FALSEUSR## somewhere!

- As the user ID FALSEUSR## was newly involved into the investigation,
  and did the 'critical things', it might make sense to additionally
  execute a behavior analysis for the user FAKEUSR##, and add
  corresponding additional log events from that step into your
  investigation (see chapter [3.3.5](#tab-behavior-analysis)). You
  should find additional log events to things, which user FAKEUSR##
  additionally did, and which were not involved as triggering events
  within alerts in the investigation.

- Lastly, finalize the Investigation. Click "Edit", update the header
  information as needed, set status to "completed", activate "Customer
  Notification", and save.
  ![](media/image94.png)

This closes the investigation, and no more changes are possible.

- At the same time, an Investigation Record is created (and a link sent
  via mail to a mail address which can be maintained in Cloud Cockpit.
  This may take a couple of minutes.

This concludes the *SAP Enterprise Threat Detection, public cloud* part
of the threat countering process. The further proceedings would now be
in the hands of the investigations report processor(s) (see next
chapter), who may involve their security team to take action on the
system users and physical persons behind them.

# Consumer/Processor role: Work with Investigation reports

Go to Tile 'Download Investigation Reports'. After a while, you will
find your investigation report in the list. Clicking on the small arrow
on the right side of the list opens the Meta data of the investigation.

![](media/image95.png)

There you can download the investigation report as a pdf document,
containing all explanations and data entered as evidences.

![](media/image96.png)

**Note:** The entering of closing remarks, and final judging by the
responsible (e.g. System Admin, Security Responsible for a system or
system landscape), is done in another role, and is Demo only (see
below).

The report you download then looks like:

![](media/image97.png)

**This part of the exercise is Demo only!**

You are now switching to your 3^rd^ role as consumer/processor of the
final product, the investigation report.

Logon to the consumer view of SAP Enterprise Threat Detection, cloud
edition .

You see the starting page for the consumer/processor role. It contains
some view-only tiles, provided for corresponding transparency, if the
analysis is provided by a service. The processor role does hence not see
the analysis tiles.

![](media/image98.png)

Click on Tile 'Download Investigation Reports'

In the opening list UI, find your investigation (i.e. with your
description), provided by you in your role as a security analyst.

![](media/image99.png)

By clicking on the small arrow, the Details-UI opens. By using the
'Download Investigation Report', a PDF document is downloaded. It
contains all evidences (recommendations, comments, Alerts, triggering
events)

![](media/image100.png)

An example report looks like:

![](media/image97.png)

The Download activity can be seen in the 'Download History' Section

![](media/image101.png)

By clicking on the 'Edit' Button, the entry fields can be changed. The
processor of the Investigation Report can here enter his own status
about mitigation of the incidents, which are analyzed by the security
specialist.

![](media/image102.png)

![](media/image103.png)

You can play around with filling the different fields, and save it.

![](media/image104.png)

**Information:** After selecting the Report to the status 'Closed', it
cannot be re-edited again, as to compliance reasons.

Additionally, you can add tags with search keywords, on which you can
easily search in the Report list.

![](media/image105.png)

Enter a tag value, and enter the 'Create' Button.

![](media/image106.png)

Afterwards, you find the tag value in the 'Details'-UI.

![](media/image107.png)

And, going back to the list, you find the tag in the list entry, and you
can search for it

![](media/image108.png)
