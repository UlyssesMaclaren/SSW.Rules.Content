---
type: rule
title: Do you ensure Zendesk is not marked as spam?
uri: do-you-ensure-zendesk-is-not-marked-as-spam
created: 2019-12-06T22:00:10.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 73
  title: Kaique Biancatti

---

Zendesk is being used everywhere now, and it is good! To ensure you are receiving important internal tickets, you need to whitelist your Zendesk domain in your primary email server.
 
​If you are using Exchange, you can do this by doing the following:

1. Go to your Exchange Admin Center (if Office 365, https://outlook.office365.com/ecp/);
2. Mail Flow | + icon | Bypass spam filtering:

![ Bypass spam filtering setting in Exchange](bypass-spam-filtering.png)

3. On the new window that opens, type a good name for the rule | Apply this rule if... | domain is | type your Zendesk domain (in our case, ssw.zendesk.com):

![ Adding domain to bypass list​](adding-domain-to-bypass-list.png)

4. The rest should already be correctly configured, hit Save

Done! You now allow any Zendesk emails through your server correctly. No more missing important tickets!"
