# Panorama DLP Installer
## Skillet to configure Panorama for use with the Enterprise DLP Service & validate Panorama is ready to build policies using advanced DLP Data Profiles and Data Patterns

***This Skillet should ONLY be run against Panorama!***

This Skillet performs the following tasks in sequence, and will stop upon failure at any step:
1. Checks that the Cloud Services Plugin version 1.6.0 or greater is installed on Panorama
    - If needed, calls the dlp-install-cloud-services-plugin to install Cloud Services Plugin v 1.6.0

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

## Authors

* Jon Farkas ([@jonfarkas](https://github.com/jonfarkas)) 
* Scott Shoaf ([@scotchoaf](https://github.com/scotchoaf))
* Nathan Embery ([@nembery](https://github.com/nembery))

## Support Policy

The code and templates in the repo are released under an as-is, best effort,
support policy. These scripts should be seen as community supported and
Palo Alto Networks will contribute our expertise as and when possible.
We do not provide technical support or help in using or troubleshooting the
components of the project through our normal support options such as
Palo Alto Networks support teams, or ASC (Authorized Support Centers)
partners and backline support options. The underlying product used
(the VM-Series firewall) by the scripts or templates are still supported,
but the support is only for the product functionality and not for help in
deploying or using the template or script itself. Unless explicitly tagged,
all projects or work posted in our GitHub repository
(at https://github.com/PaloAltoNetworks) or sites other than our official
Downloads page on https://support.paloaltonetworks.com are provided under
the best effort policy.
