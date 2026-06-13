The repository contains a POC of SOC lab setup with custom rules.

In the /var/ossec/etc/rules/local_rules file write the custom rules.The rules covers from

Group: linux
Rule     IDLevel      What it detects
100001   5            SSH brute force — 15 failed attempts in 60s from same IP (10.0.2.15), parent rule 5712
100002   10           Privilege escalation — non-sudoer trying to run as root, parent rule 5405
100003   13           Log tampering — file deleted/modified under /var/log, parent rule 553
200400   7            Nmap scan detected — matches decoded_as: nmap with host/protocol fields


Group: windows
Rule     IDLevel      What it detects
100534   3            PowerShell activity — any event from PowerShell provider, parent rule 60009

Group: syslog,sshd
Rule     IDLevel      What it detects
100009   5            Invalid SSH login attempt — matches "illegal user" or "invalid user" strings, parent 5700




The file integrity monitoring is a feature in wazuh  that ensures real time monitoring of file "/var/log" any change in "/var/log " triggers this rule
