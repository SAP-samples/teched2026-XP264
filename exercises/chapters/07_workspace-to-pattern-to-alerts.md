# From Workspace to Pattern to Alerts

## Understanding Patterns

- Return to the Console Home Screen and Enter the "Manage Patterns" app.

- Choose to "Create Pattern" and in the pop-up maintain the relevant
  information. Importantly, set the status to "Active", frequency to the
  lower limit of 5 minutes; and Threshold to \>=1. In the "Chart" field,
  retrieve and assign the Chart you have created.

![](../media/image81.png)

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

![](../media/image82.png)

As it is a custom Pattern, there is no predefined SAP template,
delivered for standard content.

Now, you create a Recommendation Template for your own Pattern, to use
it later in the Investigation handling when clicking on 'Generate
Recommendation'. Click the 'Edit Button' again, click on tab 'Custom
Template', then click on button 'Create'.

![](../media/image83.png)

Into chat field, enter a small ask, like 'Create a SOP'. (SOP stands for
Standard Operation Procedure). **Note:** As the AI cannot find out the
content about generic attributes (like 'Parameter Name', Parameter
Value, String, ..), you can as well provide hints (Like: 'Information:
Parameter Value contains the Business Partner ID') to be recognized in
the recommendation text.

Then press the button to start the generation.

![](../media/image84.png)

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

![](../media/image85.png)

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

![](../media/image86.png)

Click the 'Save Button'. Your Pattern is finished.

Finally, in the resulting screen, trigger the button "Execute" to run
the pattern on the logs in the hot storage (evaluating past logs for the
event happening), and generate Alerts.

![](../media/image87.png)

- Finally, return to the Manage Alerts app. Filter for Alert(s)
  pertaining to your pattern xx_PWHashAttack. Have a look at the
  "trigger" field, detailing the resource and the user (pseudonym)
  responsible for creating the alert (if necessary, expand the
  text/field).

Your Alert looks like:

![](../media/image88.png)

- Mark the alert(s), and add them to your Investigation, by filtering
  the alerts related to the user pseudonym (Acting) in your alert
  created by your own pattern.:

![](../media/image89.png)

In the following screen, press "Add and Show Investigation":

![](../media/image90.png)

---
Prev: [5. User & Environment Behavioral Analysis](06_behavioral-analysis-forensic-lab.md) | Next: [7. Finalize the Investigation](08_finalize-the-investigation.md) | [Contents](../README.MD)
