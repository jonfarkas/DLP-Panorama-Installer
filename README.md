# DLP-Verify-Panorama
Validation Skillet to test whether Panorama is connected to the Enterprise DLP Service 
and ready to build policies leveraging advanced DLP Data Profiles and Data Patterns

This Skillet should ONLY be run against Panorama 



This Skillet performs the following tasks in sequence, and will stop upon failure at any step:
1. Checks that the Cloud Services Plugin version 1.5.0 or greater is installed on Panoramaa

2. Checks that Panorama has a connection to the Enterprise DLP service
***Important Note*** : If the DLP service trial has not been requested in Panorama, the same
command that checks will also request a trial of the DLP service.  
DO NOT RUN THIS SKILLET IF YOU DO NOT WANT TO CONNECT TO THE DLP SERVICE
(but then, why would you be running this skillet, right?)

3. Checks that several expected predefined Data Profiles configured by the Enterprise DLP service
are seen in the device group "Remote_Network_Device_Group" (this device group is created by the cloud 
services plugin) with expected data patterns referenced in their first rule.  

Predefined Data patterns that are checked:
    - Bulk CCN
    - Corporate Financial Docs
    - Financial Information
    - GDPR
    - GLBA
    - Healthcare
    - Intellectual Property
    - Legal
    - Malware
    - PII
    - Profanity
    - Sensitive Content
    - U.K. PIOCP

If any of the above profiles are missing, the skillet will list out each missing predefined skillet is not found.