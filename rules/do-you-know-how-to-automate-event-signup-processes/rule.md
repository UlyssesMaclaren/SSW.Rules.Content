---
type: rule
title: Do you know how to automate event signup processes?
uri: do-you-know-how-to-automate-event-signup-processes
created: 2017-02-27T00:36:43.0000000Z
authors:
- id: 4
  title: Ulysses Maclaren

---

You should automate signup processes using [Zapier](https&#58;//zapier.com/).



 
This is the process of a soon-to-be attendee Mr. Northwind signing up for an event:



1. Mr. Northwind visits one of the event pages, e.g. [http://xamarinhackday.com/](http&#58;//xamarinhackday.com/)
2. He presses sign up on [http://xamarinhackday.com/register/](http&#58;//xamarinhackday.com/register/)
3. After selecting a city, he presses register now on [http://xamarinhackday.com/sydney/](http&#58;//xamarinhackday.com/sydney/)
4. He registers for the event on Eventbrite, e.g. [https://www.eventbrite.com/e/xamarin-hack-day-sydney-tickets-20718021159?aff=erelexpmlt](https&#58;//www.eventbrite.com/e/xamarin-hack-day-sydney-tickets-20718021159?aff=erelexpmlt)





This is the according internal process:

1. A Zapier Zap puts his data into a list in Active Campaign and enriches it with tags (e.g. Angular, 2-Day-Angular-Melbourne-Mar-17)
2. Mr. Northwind’s data is sent to a custom web hook receiver (his phone number, email address, full name, and tags are taken from Active Campaign), which adds it to our CRM
