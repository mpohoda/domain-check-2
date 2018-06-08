Domain Expiration Check Shell Script
====================================
A simple shell script to display or notify the user via email about domain status and expiry date. 

Installation:
-------------
Use the curl or wget command to grab script as follows:

```
$ wget https://raw.githubusercontent.com/mpohoda/domain-check-2/master/domain-check-2.sh
## [ sample domain list for testing purpose ] ##
$ wget https://raw.githubusercontent.com/mpohoda/domain-check-2/master/domain-list.txt 
## [ install it in /usr/local/bin dir ] ##
$ sudo cp -vf domain-check-2.sh /usr/local/bin/domain-check-2
$ sudo chmod +x /usr/local/bin/domain-check-2.sh
```

Usage:
------
Run it as follows:
```
$ domain-check-2 -d google.com
$ domain-check-2 -d cyberciti.biz
$ domain-check-2 -f domain-list.txt 
```
Sample outputs:
```
Domain                              Registrar                                      Status   Expires     Days Left
----------------------------------- ---------------------------------------------- -------- ----------- ---------
affplanet.com                       Wild West Domains                              Valid    19-jan-2019   225  
beezdesk.com                        PSI-USA, Inc. dba                              Valid    04-may-2019   330  
getreply.com                        Wild West Domains                              Valid    17-oct-2019   496  
ladesk.com                          Wild West Domains                              Valid    01-may-2025   2519 
liveagent.jp                        interwork                                      Expiring 30-jun-2018   22   
liveagent.se                        Ascio                                          Valid    19-nov-2018   164  
liveagent.sk                        Quality Unit                                   Valid    30-oct-2022   1605 
postaffiliatenetwork.com            Wild West Domains                              Valid    16-feb-2019   253  
postaffiliatepro.com                Wild West Domains                              Valid    20-may-2025   2538 
qualityunit.com                     Wild West Domains                              Valid    29-oct-2022   1604 
unitminer.com                       Wild West Domains                              Valid    29-oct-2022   1604 
websialive.com                      Tucows Domains In                              Valid    01-apr-2019   297  
```
[Setup Unix/Linux cron job](https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/)  as follows to get email notification to send expiration notices:

```
@daily /path/to/domain-check-2.sh -f /path/to/your-domains.txt -e you@example.com
```
Getting help
------------
```
$ domain-check-2.sh -h
Usage: domain-check-2.sh [ -e email ] [ -x expir_days ] [ -q ] [ -a ] [ -h ]
          {[ -d domain_namee ]} || { -f domainfile}

  -a               : Send a warning message through email 
  -d domain        : Domain to analyze (interactive mode)
  -e email address : Email address to send expiration notices
  -f domain file   : File with a list of domains
  -h               : Print this screen
  -s whois server  : Whois sever to query for information
  -q               : Don't print anything on the console
  -x days          : Domain expiration interval (eg. if domain_date < days)
```

Authors:
--------
* Origianl Author: Matty < matty91 at gmail dot com > https://github.com/Matty9191
* Forked and maitained by nixCraft https://www.cyberciti.biz/tips/domain-check-script.html 
* I added support and fixed for various C/TLDS.
