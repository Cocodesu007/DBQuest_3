Implementation Plan - Securing Credentials
I will move the sensitive SMTP credentials from 
send_mail.php
 to a separate configuration file (config.php) and ensure this file is ignored by Git.

User Review Required
WARNING

Credential Rotation: If you have already pushed 
send_mail.php
 or 
phpmailer/mail.php
 with the password to GitHub, changing it now in the code will NOT remove it from your commit history. You must:

Change your Gmail password (or App Password) immediately.
Consider scrubbing the history (complex) or deleting the repo and pushing fresh (easier if early in project).
This plan only protects future pushes.
Proposed Changes
Configuration
[NEW] config.php
A PHP file returning an array of settings.
Contains SMTP_HOST, SMTP_USER, SMTP_PASS, etc.
[NEW] .gitignore
Add config.php to this file.
Add other common ignores (e.g., node_modules/, vendor/, .vscode/).
Backend
[MODIFY] 
send_mail.php
Include config.php.
Replace hardcoded strings with variables from the config.
Verification
Start the server.
Send a test email via the contact form.
Verify email is sent (proving config.php is read correctly).
Check git status (if git is initialized) to confirm config.php is ignored.