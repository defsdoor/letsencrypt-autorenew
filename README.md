# letsencrypt-autorenew
Script to allow automatic renewal of all letsencrypt certificates.

Simply create a control file (/etc/letsencrypt/mycerts) containing the certificate details you require. 
Multiple certificate can be defined in the same file - each new occurance of either the HOSTS or EMAIL keywords determine a new certificate.

When run, it checks for the presence of each existing certificate and then compares its details with the settings in the control file.

If the certificate does not exist, or has a different list if Alternate Subject Names, or expires in less than 8 days, a new certificate will be requested.

Add this to cron to run daily and email the output to yourself.
