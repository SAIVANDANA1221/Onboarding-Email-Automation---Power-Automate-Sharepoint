# Onboarding-Email-Automation---Power-Automate-Sharepoint
# Overview
This project implements an automated onboarding communication system using Microsoft Power Automate and SharePoint Lists.
The automation sends onboarding emails to new employees during their first week and ensures proper scheduling even when HR enters incorrect dates such as weekends or holidays.
The workflow also automatically cleans up completed records once the onboarding sequence finishes.

# Key Features
1. Automated onboarding email sequence (Day 1 – Day 5)
2. Handles incorrect HR start dates (weekend adjustments)
3. Skips company holidays automatically
4. Prevents duplicate emails using tracking fields
5. Supports bulk employee upload via SharePoint Grid View
6. Automatically removes completed onboarding records
7. Timezone-aware scheduling (US Eastern Time)

# Technologies Used
1. Microsoft Power Automate
2. SharePoint Online
3. Microsoft 365

# Automation Logic
The flow runs daily and follows this logic:
1. Trigger runs at 10:00 AM ET.
2. Fetch employee records from SharePoint.
3. Adjust the hire date if HR enters a weekend.
4. Calculate the number of days since onboarding started.
5. Send the correct onboarding email.
6. Update the tracking column for the email sent.
7. Skip sending emails if the current day is a holiday.
8. Automatically delete the record after the onboarding sequence completes.

# Holiday Handling
If a scheduled email day falls on a company holiday:
1. The email is skipped
2. The corresponding column is marked Holiday
3. The automation continues the next business day

# Bulk Employee Upload
Employees can be added in bulk using SharePoint Grid View.
Steps:
1. Open SharePoint List
2. Click Edit in Grid View
3. Copy employee data from Excel
4. Paste directly into SharePoint
5. Save the list

# Cleanup Automation
Once the onboarding sequence finishes, the system automatically removes the employee record from the list.
This ensures the list remains clean and only contains active onboarding users.

# Flow Architecture
Recurrence Trigger -> Get Employees from SharePoint -> Apply to Each Employee -> Adjust Start Date (Weekend Fix) -> Calculate Days Since Start -> Switch Case (Day 1–Day -> Holiday Check -> Send Email + Update Tracking Field -> Delete Completed Records

# Benefits
1. Eliminates manual onboarding follow-ups
2. Ensures consistent employee communication
3. Handles HR input inconsistencies
4. Reduces administrative overhead

# Future Improvements
Possible enhancements:
1. Business-day calculation for holidays automatically
2. Logging system for sent emails
3. Dashboard reporting for onboarding status
4. Integration with HR systems

# Author
Saivandana Unukonda
Automation Developer – Power Platform
