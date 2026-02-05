Implementation Plan - GD Fix & Form Styling
Problem Summary
Fatal Error: Call to undefined function imagecreatetruecolor() means the PHP GD extension is disabled in XAMPP.
UI Issue: The <select> dropdown inside .form-group has white text on a white background (or transparent), making it unreadable.
User Action Required
IMPORTANT

You must enable the GD extension in XAMPP manually. I cannot edit your XAMPP configuration files safely.

Open XAMPP Control Panel.
Stop Apache.
Click Config (next to Apache) -> PHP (php.ini).
Press Ctrl+F and find ;extension=gd.
Remove the ; at the beginning of the line so it becomes extension=gd.
Save the file and Start Apache again.
Proposed Changes
CSS Fixes
[MODIFY] 
css/contact.css
Target .form-group select or option.
Ensure the background color is dark (or matching theme) and text is readable.
Since the overall input style is likely dark/glassmorphic, the default dropdown (<option>) often defaults to system white unless styled explicitly.
Verification Plan
Captcha: User restarts Apache and reloads 
captcha.php
. The error should disappear and show an image.
Select Dropdown: Reload 
contact.html
. Click the "You are a" dropdown. The options should have a dark background with light text.