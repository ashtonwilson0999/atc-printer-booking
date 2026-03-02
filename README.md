**ATC 3D PRINTING RESERVATION SYSTEM:**
A lightweight, web-based booking system for the ATC lab, powered by GitHub Pages and Google Sheets.

**QUICK LINKS:**
Public Booking: https://your-username.github.io/index.html
Staff Dashboard: https://your-username.github.io/dashboard.html

**SYSTEM ARCHITECTURE:**
This system is "serverless," meaning it doesn't require a paid database.
Frontend: HTML/CSS/JS hosted on GitHub Pages.
Backend: Google Apps Script (GAS) acting as a bridge.
Database: A Google Spreadsheet storing all bookings, machine statuses, and student penalties.

**STAFF ACCESS & SECURITY:**
Password: The current staff password is set in both dashboard.html and the Google Apps Script.
Authentication: The dashboard uses sessionStorage. Staff must log in once per session. Closing the tab logs the user out.
Current Password: ATC_SPRING_2026

**MAINTENANCE & TROUBLESHOOTING:**
To Change the Staff Password:
Open the Google Apps Script editor and update the staffKey variable.
**Crucial:** Click Deploy > Manage Deployments > Edit > Version: New Version > Deploy.
Update the MASTER_PASS constant in dashboard.html to match.

If a Printer Breaks:
Log into the Staff Dashboard.
Click the status button for the machine (e.g., Change ONLINE to OFFLINE).
The booking.html page will automatically gray out that printer and prevent new reservations until it is toggled back.

Managing No-Shows:
The system tracks email addresses in the Penalties tab of the Google Sheet.
Staff can click Mark No-Show on the dashboard to increment a student's count.
Per lab policy, students lose privileges after 3 no-shows.

**SPREADSHEET STRUCTURE:**
Do not rename the following tabs in the Google Sheet, or the system will break:
Bookings: All raw reservation data.
Status: Current machine availability (Super7 and SCARA).
Penalties: Tracks student email addresses and their no-show counts.

**DEVELOPER NOTES:**
To update the UI or styling, edit the CSS within the <style> tags of index.html, booking.html, or dashboard.html. All logic is handled via vanilla JavaScript (ES6).
