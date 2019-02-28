---
title: Getting notifications from your Raspberry Pi
published: false
---

Here are two ways of receiving notifications from you Raspberry Pi Python scripts.

## Email
Sending simple notifications to your email address is quite easy if you aren’t bothered about formatting text in fancy ways.

Here is the code to send yourself an email with a subject and a body:

```
import smtplib
SUBJECT = "The subject"
MESSAGE = "The message"
msg = "Subject: %s\n\n%s" % (SUBJECT, MESSAGE)
server = smtplib.SMTP('smtp.gmail.com', 587)
server.starttls()
server.login("{EMAIL USERNAME}", "{EMAIL PASSWORD}")
server.sendmail("{FROM EMAIL ADDRESS}", "{TO EMAIL ADDRESS}", msg)
server.quit()
```
The above example uses Gmail’s server to send the email but you can use what ever service you use.

The `msg` variable just defines the subject of the email and the body separately.

`{EMAIL USERNAME}` and `{EMAIL PASSWORD}` refer to your email servers details. In Gmail’s case, this is your Gmail email address and password.

`{FROM EMAIL ADDRESS}` should be the email address you are sending the email as.

`{TO EMAIL ADDRESS}` should be the email address you are sending the email to. It can be the same email address as you sent it with to send it to yourself. You can also send to multiple addresses with a list. E.g `["email1@example.com", "email2@example.com"]`.

---

## Android Push Notifications
If you want quick updates on tasks run and errors that your Pi has encountered, then download Simple Push on your android device. This app takes GET requests and sends you push notifications.

When you first open the app, it will give you a unique code. Keep this handy.

Here is the code for sending a notification from a python script to your phone or tablet:

import requests
title = "A title for your notification"
body = "Your notifications main text"
requests.get("https://api.simplepush.io/send/{YOUR UNIQUE ID}/" + title + "/" + body)
For me, these two methods suffice for getting the information from my python scripts. If you have any other methods, let me know and I can add them to this post.
