# Jamf Restricted Software Automation Script #

![image](https://github.com/user-attachments/assets/2a6ba08b-f99f-4bdc-a0a9-3866456020c4)

**Overview**
This script automates the identification and restriction of unauthorized software in a Jamf Pro environment. It analyzes applications installed on managed devices, compares them to a whitelist, and restricts unauthorized applications exceeding a specified usage threshold. Additionally, it generates a log report and sends an email summary with details of restricted applications.

**Features**
Automated Restricted Software Management
Automatically identifies and restricts software not in the whitelist.

**Whitelist Support**
Skip restriction for applications listed in the whitelist.

**Threshold-Based Restriction**
Only restrict applications with a usage count exceeding 5.

**Dual Mode Operation**
Testing Mode: Simulates restrictions without making changes to Jamf.
Live Mode: Applies restrictions to Jamf.
Reporting
Generates a log file (.csv) detailing restricted applications.

**Email Notifications**
Sends an email summary of restricted applications, including an HTML table, log attachment, and optional image.

**Prerequisites**
Jamf Pro API Credentials
Ensure you have valid Jamf API credentials (username/password or client ID/secret).

**Email Configuration**

SMTP server details.
Email credentials for sending notifications.
Inventory Settings in Jamf Pro
Ensure that the home directory is scanned during inventory check-ins to capture user-installed applications.

**Example Inventory Settings in Jamf Pro:**
Include this image in your repository:

**Installation**
Clone this repository:

bash
Copy code
git clone https://github.com/your-username/jamf-restricted-software.git
Update the script with your environment-specific values:

Replace username and password with your Jamf API credentials.
Replace https://server.jamfcloud.com with your Jamf Pro server URL.
Update $recipients with the email addresses for notifications.
Update the $whitelist array with applications that should not be restricted.
Place the script in a secure location on a server or management workstation with PowerShell.

**Usage**
Script Modes
Set the $Mode variable to:

Testing: Simulates restrictions without modifying Jamf.
Live: Updates Jamf with newly restricted applications.
Run the Script
Open PowerShell as an administrator.
Execute the script:
powershell
Copy code
.\Create-JSSRestrictedSoftware.ps1
Expected Outputs
A .csv log file in C:\Temp\ detailing the results.
Email notifications sent to the specified recipients.
Email Notification Example
Below is an example of the email notification generated by the script:

Subject: Jamf Restricted Software Summary

Body:

Includes a GIF or image.
Displays restricted applications in an HTML table.

**Configuration Details**
Environment Variables
API URL: Update the $url variable with your Jamf Pro server URL.
Authentication: Use Basic Authentication (username/password) or update the script to use Client ID/Secret.
Whitelist
Define applications in the $whitelist array to exclude them from restrictions.

**Logs and Error Handling**
Logs are saved in C:\Temp\ with filenames following the pattern: RestrictedSoftwareAnalysis_YYYYMMDD_HHMMSS.csv.
Errors are logged to C:\Temp\ErrorLog.txt.
Known Issues
Ensure the script has the necessary permissions to access Jamf API endpoints.
The inventory scan must include the home directory for accurate application detection.
Future Enhancements
Support for additional thresholds or conditions.
Improved error handling and debugging tools.
Extended logging options with customizable output formats.
Contributors
Author: P. Sassmannshausen
Co-Author: ChatGPT
License
This project is licensed under the MIT License.

Screenshots
Jamf Inventory Collection Settings

Email Notification Example

Feel free to modify the placeholders (path-to-your-image-file, path-to-your-email-image, etc.) with the actual file paths for your images and adjust any text as needed!
