---
layout: post
title: Google Forms automatic Calendar and Email
---
http://www.jessespevack.com/blog/2016/2/9/turn-a-google-form-response-into-a-calendar-event
https://snipe.net/2013/04/26/email-contents-google-form/
https://github.com/dwyl/html-form-send-email-via-google-script-without-server
https://developers.google.com/apps-script/reference/mail/mail-app


http://www.jessespevack.com/blog/2016/2/9/turn-a-google-form-response-into-a-calendar-event
https://developers.google.com/apps-script/articles/sending_emails
https://developers.google.com/apps-script/reference/mail/mail-app


I am part of the Staff of a [Scout Center](http://apulia.cne-escutismo.pt/) (think Camping Park for Scout groups) and we wanted to streamline our booking process.

Right now, to book a reservation one would need to send us an email saying they wanted to camp on our site, we would need to read their email message, look at the calendar, create an event for that booking and responde to the email message.

Right now, the booking process is something like this:
  1. someone sends us an email message saying theyy want to camp on our site;
  2. *we read* their email message;
  3. *we look* at the calendar to check availability and create an event for the booking request;
  4. *we reply* to the email message confirming the availability and asking additional mising information.

That's too much work for *us* :tired_face:. Some steps can be automatic :link:.

We wanted to switch to a Google Form to collect the booking requests, instead of email messages. This would us to ask right way the information we need and receive it right on the first contact.

Then it was a matter of searching for ways to automatically get notified when a new request comes in. Additionally, the automatic process should also create an event with the booking request on our calendar.

Although [there is a simple way](https://www.labnol.org/internet/email-notification-for-google-docs-forms/5248/) to do that, what we wanted was a bit more advanced: receive an email message to our booking address with the details of the booking request, and that email message should also be sent to the person responsable for the booking.

A little Googling around :mag: and Google Apps Script seemed to be the answer. Great, a solution within the same family: Google Forms, GMail, Google Calendar, Google Apps Scripts :link:.

The first search result I got was [this article ("Turn a Google Form response into a Google Calendar event")](http://www.jessespevack.com/blog/2016/2/9/turn-a-google-form-response-into-a-calendar-event) very detailed article.
