---
layout: post
title: "Linux | Cron Basics"
published: false
tags: [resource]
---

## What is Cron?
Cron is a job scheduler that is available on Linux and Unix operating systems. Simply, you tell it when to run a task and it will run.
Cron will run bash terminal commands that you set it to run but these can be set to run larger programs like python scripts, backup procedures, automation etc.

## Edit cron jobs
In a terminal or on the command line, enter `crontab -e`. The `-e` means 'edit'. You can see what cron jobs are installed by entering 'crontab -l'.

Cron jobs have a particular format that describes the time in which they run then the command to run. A typical cron job will look like this: `0 1 * * * sudo reboot`.

Each number or asterisk represents a unit of time. Here is what each star represents:
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

<!-- The asterisk means that the command will every time. For example `* * * * * sudo reboot` will reboot the machine every minutes of every hour of every day of every week of every month. -->

## Special Characters
There are some special characters that can be used with the numbers to run commands at more specific times.

- Slash `/` - Used in the hour or minute place. It means EVERY.
- Comma `,` - Used to create a list.
- Hyphen `-` - Used to create a range.

Examples:

`15-45/5 * * * * echo Hello!` - Will run every 5 minutes between 15 minutes past and 45 minutes past the hour. This will run every hour.

`0 10,11,12 * * 1-5` - Run Monday to Friday (1-5) at 10:00, 11:00 and 12:00.

`0 9-17 * * *` - Run every hour, nine to five.