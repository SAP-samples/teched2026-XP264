# Finalize the Investigation

You can now conclude the Investigation.

- In the app for "Manage Investigations", you will find the header
  information you have maintained before and can edit. You may choose
  "edit" in case you desire to change the information.

- In the middle section, click on "Alerts". Here, you can research the
  Alerts, have a look at some of the complete triggers explanation texts
  and how they codify the core findings in this text. You may also
  review some of the triggering Events.

![](../media/image91.png)

- In the Trigger text, you may also come across additional user
  pseudonyms or references to IP addresses from where the triggering
  actions were initiated. These can be valuable leads to follow up on --
  If you have time left, you may note down the pseudonyms (or also users
  in clear) and IP addresses, return to the Manage Alerts app, search
  for more Alerts involving these pseudonyms, and add the results to
  your Investigation.

![](../media/image92.png)

- Finally, return to your Investigation. You may comment/document what
  actions you have been performing, and what deductions these allow.

- Then return to the tab for "Users". For each pseudonym, trigger the
  de-pseudonymization:

![](../media/image93.png)

- This will reflect in the "Actions" tab -- have a look at the clear
  user names. You should be spotting your FALSEUSR## somewhere!

- As the user ID FALSEUSR## was newly involved into the investigation,
  and did the 'critical things', it might make sense to additionally
  execute a behavior analysis for the user FALSEUSR##, and add
  corresponding additional log events from that step into your
  investigation (see chapter [3.3.5](04_checking-alerts-and-investigations.md#tab-behavior-analysis)). You
  should find additional log events to things, which user FALSEUSR##
  additionally did, and which were not involved as triggering events
  within alerts in the investigation.

- Lastly, finalize the Investigation. Click "Edit", update the header
  information as needed, set status to "completed", activate "Customer
  Notification", and save.
  ![](../media/image94.png)

This closes the investigation, and no more changes are possible.

- At the same time, an Investigation Record is created (and a link sent
  via mail to a mail address which can be maintained in Cloud Cockpit.
  This may take a couple of minutes.

This concludes the *SAP Enterprise Threat Detection, public cloud* part
of the threat countering process. The further proceedings would now be
in the hands of the investigations report processor(s) (see next
chapter), who may involve their security team to take action on the
system users and physical persons behind them.

---
Prev: [6. From Workspace to Pattern to Alerts](07_workspace-to-pattern-to-alerts.md) | Next: [8. Consumer/Processor role](09_consumer-processor-role.md) | [Contents](../README.MD)
