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

![](../media/image54.png)

## Build up a Workspace

- Return to the monitoring console of SAP Enterprise Threat Detection,
  cloud edition.

- Go to the app "Forensic Lab".

> ![](../media/image55.png)

- In the area "Custom Workspaces", you see a list of existing
  workspaces.

- Create a new Workspace with Name ##TechEdPWHashAttack, by replacing
  the \## with your participant number. Enter some additional
  information (Use case, Severity, Description), and then click on
  'Create'

> ![](../media/image56.png)

- Then the your new Workspace arrives in the Workspace list, and is
  opened automatically to continue working. To open it later, you can
  click on the name link in the list, or on the arrow on the right for
  your Workspace.

![](../media/image57.png)

- Your new workspace contains already a first Filter Path (Path 1) with
  a subset (Subset 0) to filter on the time range.

- Click on the 'Refresh' Button
  ![](../media/image58.png)to see incoming log data.

- Click into the Subset 0, to get some Symbols at the right

- Click into the Pi-Chart Symbol to view the data in a chart preview.
  You see as a default the distribution of log events, related to their
  systems

- By clicking on the Drop-Down-Symbol, you can select other attributes
  of the ETD normalized Data Model

> ![](../media/image59.png)
>
> By e.g. selecting 'Event (Semantic)' you get a distribution of all log
> events, related to the Semantic Events.
>
> ![](../media/image60.png)

- By clicking the 'Edit' Button
  ![](../media/image61.png),
  you start modelling your workspace. You see now some additional
  Symbols at the right of your Subset 0.

- Change the relative Timestamp of Subset 0 to 2 hours by clicking on
  the symbol 'Edit Subset'
  ![](../media/image62.png)

> ![](../media/image63.png)
>
> ![](../media/image64.png)
>
> ![](../media/image65.png)
>
> ![](../media/image66.png)

**Information:** [To be able to see some data in the following filter
steps, directly before the session started, all FALSEADM## users in the
S4/H system got a mass change by adding a high privilege.]{.mark}

- By clicking on the 'Create Subset'
  ![](../media/image67.png) Symbol, a Popup appears to enter the
  filter criteria for the next subset. Please enter:

  - Semantic Attribute: Event (Semantic)

  - Type: Value

  - Operator: Equal

  - Value: User Admin, Privilege, Grant

- Then click 'Apply'.

- ![](../media/image68.png)

- Your new Filter Subset 'Subset 1' appears. By clicking into the Subset
  1, you can use the small symbols at the side (especially the Pie-Chart
  Symbol) to do a preview on the data filtered in Subset 1 in the
  Preview area.

- Then click on the 'Save' Button

> ![](../media/image69.png)

- Create a new Subset
  ![](../media/image67.png) to filter (for Demo Purposes) on your
  own ABAP User FALSEADM\<YourNumber\>. In the Popup enter:

  - Semantic Attribute: User Pseudonym, Target

  - Type: Value

  - Operator: Equal

  - Value: FALSEADM\<YourNumber\>

- Then click on 'Create'

> ![](../media/image70.png)

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

![](../media/image71.png)

- You new Subset is showing as 'Subset 3'. By refreshing and selecting
  the Pie Chart you can see some data in Subset 3.

**Information**: The value list AuthorizationCriticalAssignmentProfiles
contains typical predelivered values for Profiles (e.g. SAP_ALL,
SAP_NEW, ...). The filter is then set as an 'IN'-filter about all
values.

To be able to correlate the provisioning of a high privilege with the
miss-use of the privilege (in the example: look up Password hashes), a
second filter path needs to filter on that activity, and then correlate
to the high privilege provisioning (via reference filter).

- Click the 'Create Path' Symbol

![](../media/image72.png)

- Select the Context 'Log' and 'save'. Your second filter path 'Path 2'
  is created and already contains a timestamp filter in Subset 0.

- Again, change the timestamp filter to Last 2 hours (to be able to see
  some data). Then you can click the 'Refresh' symbol and the
  'Pie-Chart' symbol to see the data of Path2, Subset 0.

> ![](../media/image73.png)

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

> ![](../media/image74.png)

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

> ![](../media/image75.png)

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

> ![](../media/image76.png)

- Your new Subset is showing as 'Subset 3' in Path 2. By refreshing and
  selecting the Pie Chart you can see some data in Subset 3.

- Finally, create a Subset, which correlates between Path 1 filter
  results for provisioning of high privileges to a **target** user, and
  path 2 results for the same **acting** user accessing a critical DB
  table with Password hashes. Use the following values:

  - Semantic Attribute: User Pseudonym, Acting

  - Type: Reference

  - Operator: In

  - Reference To: Subset 3, Path 1

  - Value: User Pseudonym, Target

- Then click on 'Create'

![](../media/image77.png)

- Your new Subset is showing as 'Subset 4' in Path 2. By refreshing and
  selecting the Pie Chart you can see some data in Subset 4. Data can be
  seen if within last 2 hours the user got a high privilege,
  [and]{.underline} in the same timeframe accessed a critical DB table.

The final result should look like this:

![](../media/image54.png)

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

![](../media/image78.png)

In the pop-up, assign a name among the lines of
"\<YourNumber\>PWHashAttack", and a description. Mark down the name.

For measurement, choose the "count" \* and a fitting Display Name if you
like:

![](../media/image79.png)

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

![](../media/image80.png)

- [Finally, click the 'Save' Button]{.mark}

> Note: Per each deviating combination of the (in this example) 4
> grouped attributes, there would arrive another bar in the bar chart.

---
Prev: [4. Trigger a Critical Action from SAP S/4HANA](05_trigger-critical-action.md) | Next: [6. From Workspace to Pattern to Alerts](07_workspace-to-pattern-to-alerts.md) | [Contents](../README.MD)
