---
layout: post
title: "Python Automation | Scheduling Scripts"
published: false
tags: [resource]
---

Here is how to either run code at either a set time every hour, day or week OR run code on boot.

# Running a script periodically

In the terminal or command line on your Pi, type crontab -e. If this is the first time doing this, it will ask you for a preferred editor (I recommend Nano). Here you can set commands to run.

For example, the cron job below will run at 1AM every day to reboot the Pi.

```
0 1 * * * sudo reboot
```

Cron jobs require a particular format in order to run the code you tell it to. Each asterisk represents a unit of time. Here is what each star represents:

```
┌───────────── min (0–59)
│ ┌────────────── hour (0–23)
│ │ ┌─────────────── day of month (1–31)
│ │ │ ┌──────────────── month (1–12)
│ │ │ │ ┌───────────────── day of week (0–6) (0 to 6 are Sunday to
│ │ │ │ │ Saturday, or use names; 7 is also Sunday)
│ │ │ │ │
│ │ │ │ │
* * * * * command
```

So if you wanted to run a python script every day at 7AM, you job will look like the code below. The job will run the three commands that have been strung together and will therefor run in sequence.

0 7 * * * cd;cd Work/get_my_ip;python ip.py

If you don’t want to string commands together, you can create a shell script that will sequence the commands instead. This may be easier to manage if there are a lot of commands or they may change regularly.

---

# Running a script on boot
It is possible to set up tasks to run on a reboot with crontabs but this has a few limitations that make it not so useful.