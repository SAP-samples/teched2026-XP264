# UI Round trip

In the 'Manage Settings' tab, users can manage system settings like retention
times and time zone etc.

![](../media/image8.png)

In the 'Value Lists' tab, users can manage value lists which are allow- or
disallow-lists where the system analyst can put custom values and even can
create custom value lists.

![](../media/image9.png)

To look into the entries of a value list, click on the corresponding
value list entry.

**Note:** Some value lists are related to special object types (like
transactions, reports, function modules, services), which allow to
retrieve additional, AI supported information about the object (what is
it, why is it security relevant, how to mitigate).

![](../media/image10.png)

Clicking on the 'see more' button provides this additional context
information.

![](../media/image11.png)

As you know: AI can provide wrong information. Then, you can provide
feedback to SAP via the 'Feedback' button, and SAP will centrally repair
the AI answer, to enhance quality.

In the 'Analyze Log Events' tab, the security analyst can view and analyze
customers' normalized log data.

![](../media/image12.png)

**Note:** If the log contains objects like transactions, reports,
function modules, services, you get an AI based support about the
object, its criticality, and possible security mitigations.

![](../media/image13.png)

In the 'Manage Alerts' tab, the system analyst can view and analyze generated
alerts.

![](../media/image14.png)

**Note:** If the Alert attributes contain objects like transactions,
reports, function modules, services, you get AI based support about
the object, its criticality, and possible security mitigations.

![](../media/image15.png)

In the 'Pattern Executions' tab, the security analyst can view and check the
status of pattern executions.

![](../media/image16.png)

In the 'Patterns' tab, the security analyst can view and create patterns (i.e.
use cases) ![](../media/image17.png)

Clicking on one of the patterns, the UI shows its overall modelling and
description.

![](../media/image18.png)

If you scroll further down, you see the existing 'Recommendation
Templates', which is used for processing corresponding alerts within
investigations. During the processing, the template is used to generate
a text by filling the placeholders.

![](../media/image19.png)

The template itself is generated with AI assistance. Customers can
overwrite SAP delivered templates, by generating their own ones, and
e.g. adding their own policies. During alert processing in
investigations, not only the template is filled and added to the report,
but as well the information about the criticality of an object,
mentioned in the alert (like transactions, reports, function modules,
services). For custom patterns, a corresponding template can be
generated as well.

In the 'Investigations' tab, the security analyst can view and manage
investigations.

![](../media/image20.png)

In the 'Record of Actions' tab, system analysts view activity logs of
the ETD system

![](../media/image21.png)

In the 'Investigations Report' tab, the security analyst can view
investigations.

![](../media/image22.png)

In the 'Forensic Lab' tile, and the Workspaces UI, the security analyst
can view and create workspaces, which are used to filter data related to
suspicious activities, and to create charts to group the data by any
criteria. Based on these charts, patterns, later raising alerts, can be
created.

![](../media/image23.png)

By clicking onto the arrow on the right at any line, you see the
modelling of the forensic workspace, related to filter paths and charts.
This is part of exercise chapter [5.1](06_behavioral-analysis-forensic-lab.md#build-up-a-workspace).

In the 'Dashboard' tile, different standard dashboards are shown, and own
custom dashboards can be created.

![](../media/image24.png)

Within a custom dashboard, any number of charts can be added from a list
of predefined charts.

![](../media/image25.png)

In the 'Manage Incoming logs' tile, the security analyst can view
incoming logs, and find out, if there are any log outages from a system
ID, or of a special log type.

![](../media/image26.png)

In the 'Resolve User Identity' tile, the security analyst can
de-pseudonymize user pseudonyms. This might be needed in case there are
evidences of a suspicious activity of a user. In order to be able to
search for the activities of a user (e.g. as to external signals), the
user's pseudonym can be determined reverse, to search for it in the log
data.

![](../media/image27.png)

---
Prev: [1. Getting started](01_getting-started.md) | Next: [2. First Log Events from SAP S/4HANA](03_first-log-events.md) | [Contents](../README.MD)
