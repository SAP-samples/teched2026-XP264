# Getting started

In this hands-on session and workshop of about 1.5 - 2h, you will get
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

In a third role, you will act as a consumer/processor of the results
(Investigation Report), that was created by you in your second role as a
security specialist.

Here's the flow of the following exercises in your roles as threat actor
and security specialist (the numbers relate to the chapters in this
document):

![](../media/image1.png)

Chapters 1 to 7 are related to these two roles. Chapter 8 is related to
the consumer/processor role.

## Logon to the Monitoring Console

Access the [*SAP Enterprise Threat Detection, public cloud* monitoring
console](https://etd-cloud-workshop-partner-nten9gd6-monitoringapprouter.prod.monitoring.etd-cloud.cfapps.eu10-004.hana.ondemand.com/cp.portal/site?targetTenantId=9189d8d0-c3ea-4f11-a145-1a7d13e32c3d&origin=monitoring#Shell-home)

**IMPORTANT:**

- You should get the below start page (if not, please empty your browser
  cache and try again).

- Here, select the first entry ("httpsetdtestlogs.accounts.ondemand") to
  log on with the generic workshop users below (not any personal
  credentials -- they won't be recognized in this cloud application).
  Do **NOT** choose the "Default Identity Provider" (here,
  the generic users won't work).

![](../media/image2.png)

User: will be provided in the session

Password: will be provided in the session

In the ensuing (logon) screen, use the ID indicated to you (01-40;
afterwards referred to as "##").

> User: Will be provided in the Session
> 
> Password: Will be provided in the session

If you inadvertently lock the password, please notify the instructor.

If you receive a blank screen saying "Where to", please clear the cache,
then close and restart the browser. You may also open a private
browsing window (often "incognito" or "InPrivate"). Log on again.

Upon initial logon, in case you get a pop-up message to select a Tenant,
then click the Select Tenant screen for selecting a specific Tenant:

As a monitoring agent providing services to multiple clients, you will
log on to your organization's own productive Tenant; however from here
commonly access and work in the specific Tenant of a client, which you
can select from this list reflecting all clients/Tenants linked to your
organization.

For this hands-on there is only one customer system linked. Click on the
blue hyperlink and select "Workshop Demo Customer".

![](../media/image3.png)

You will then see the *SAP Enterprise Threat Detection, public cloud*
monitoring console. Take a bit of time to check out a few apps and see how
they behave.

![](../media/image4.png)

## Got a Warning 'Select a tenant'

If you encounter a warning popup

![](../media/image5.png)

the system has lost the information which tenant you've been working on
(most likely you had been logged out).

In this case, either start the *SAP Enterprise Threat Detection, public
cloud* console again via the above link.

Alternatively, you can manually set the correct tenant:

- In the section for "Cross-Tenant Applications", open the app "Select
  Tenant".

- Remove filters "active" and press "go".

- The entry "Workshop Demo Customer" will show; select this so the
  system is aware which tenant you are working on - which is relevant
  in case you're a partner providing monitoring services to multiple
  clients).

![](../media/image6.png)

![](../media/image7.png)

---
Next: [2. UI Round trip](02_ui-round-trip.md) | [Contents](../README.MD)
