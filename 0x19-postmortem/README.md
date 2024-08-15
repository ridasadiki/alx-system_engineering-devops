## Postmortem

## Issue Summary
Duration:  2024, 10:00 - 11:30 (GMT)

Impact: Our Apache web server was feeling extra rebellious and decided to throw a 500 Internal Server Error party, making our website inaccessible to all users. Yes, 100% of our users were greeted with frustration during this period. We sincerely apologize for any coffee spilled out of anger.

Root Cause: Someone (let's call them "The Cleaner") accidentally deleted a critical configuration file for a custom Apache module during routine cleanup. Oops!

## Timeline

10:00 (GMT): Issue detected by our super-alert monitoring system screaming, "HTTP 500 everywhere!"
10:05 (GMT): On-call engineer tries to access the site, receives a 500 error, and promptly sighs.
10:10 (GMT): Logs are checked but reveal only vague messages – like a magic 8-ball that only says, "Ask again later."
10:20 (GMT): Misleading path: Initial suspicion falls on the database (because it's always the database, right?). Database team confirms it's not their fault this time.
10:30 (GMT): Strace is attached to the running Apache process, providing detailed system calls and finally pointing fingers.
10:40 (GMT): Strace output shows a "No such file or directory" error for a configuration file. Aha!
10:45 (GMT): Missing configuration file is identified and recreated manually, while the team does a happy dance.
11:00 (GMT): Apache is restarted, and the web server returns to normal, probably asking, "Why didn't you just do that earlier?"
11:30 (GMT): Monitoring confirms the site is back to full health. All is well, and coffee is enjoyed once more.
Root Cause and Resolution
Root Cause: The Cleaner accidentally deleted a critical configuration file for a custom Apache module. Apache, not happy with this turn of events, refused to work and threw 500 errors for all requests.

Resolution: The missing configuration file was recreated manually,
and Apache was restarted. Apache, now satisfied, resumed normal operation.


Corrective and Preventative Measures

## Improvements:

Implement automated configuration management to ensure critical
files aren't deleted by overly zealous cleaners.
Enhance monitoring to detect and alert on configuration-related errors more specifically.

## Tasks:

Automate Configuration Management: Use Puppet to ensure the critical
configuration file exists and is correctly configured.

## Improve Monitoring:

Add specific alerts for missing configuration files or module loading errors.
Enhance logging to capture more detailed error information.
