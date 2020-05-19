## Validation Skillet for Panorama - DLP Service Checks
This skillet will perform the following validations / steps in sequence:
1. Checks for Cloud Services Plugin version 1.6.0 or greater
2. Checks for DLP Service Provisioning in Panorama (note that this step will also request a trial of the DLP Service if not connected)
3. Checks for the presence of expected predefined Data Profiles and Data Patterns
    - Output is limited to only missing items, otherwise will show a summary success message

If step 1 should fail, the workflow skillet will call the dlp-install-cloud-services-plugin skillet 
to install Cloud Services Plugin 1.6.0, then re-run this skillet. 

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