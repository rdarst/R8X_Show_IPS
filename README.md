# R8X_Show_IPS
Simple script to export all IPS protections to a CSV file so that you can compare against needed coverage/CVE's

The script will login as root via the -r true flag and the login will occur as Read-Only.  Please add credentails here if you need an autorized user to execute these commands.

The IPS data will be output as a CSV file with the name "IPS_Output_Version_{{ IPS DB Version }}".  

```
Example - IPS_Output_Version_635158746
```

The fields "Industry-Reference" will be output using ; as a delimiter.  If no "Industry-Reference" is provided in the JSON output it will be replaced with "None"

The CSV file is output with the following format:
```
uid, name, severity, confidence-level, release-date, update-date, follow-up, performance-impact, industry-reference
```

To use, move the script to your management server, make it executable and run the following command for a SmartCenter

```
./show_ips SMARTCENTER
```

For a MDS (Multi-Domain), specify the Domain after the command.  For the Global Domain use "Global"

```
./show_ips Global
```

Example output from a MDS system

```
[Expert@MDS1:0]# bash show_ips Global
Logging into CMA ==> Global
Logging out of CMA/SmartCenter
OK
```
