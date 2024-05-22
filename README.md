# [*NEW* A No-Nonsense Splunk Course | Getting Started Guide](https://www.udemy.com/course/no-nonsense-course-on-using-splunk/)  

## Links  

[Splunkbase](https://splunkbase.splunk.com/)  
[What data can I index?](https://docs.splunk.com/Documentation/Splunk/9.1.2/Data/WhatSplunkcanmonitor)  
[source type](https://docs.splunk.com/Splexicon:Sourcetype)  
[List of pretrained source types](https://docs.splunk.com/Documentation/Splunk/9.1.2/Data/Listofpretrainedsourcetypes)  
[Source type configuration](https://docs.splunk.com/Documentation/Splunk/9.1.2/Admin/Propsconf#Sourcetype_configuration)  
[stats command overview](https://docs.splunk.com/Documentation/SCS/current/SearchReference/StatsCommandOverview)  
[Quick Reference for SPL2 Stats and Charting Functions](https://docs.splunk.com/Documentation/SCS/current/SearchReference/StatsFunctionsQuickReference)  

## Installation

```
General download page:
https://www.splunk.com/en_us/download.html

1 - Download Splunk Enterprise here:
https://www.splunk.com/en_us/download/splunk-enterprise.html?locale=en_us

The page provides the wget command to get .deb .rpm packages or the tar gz file. I got the tar gz:
wget -O splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz "https://download.splunk.com/products/splunk/releases/9.2.1/linux/splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz"

2 - Uncompress the file (it generates a splunk folder):
tar -xvf splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz

3 - Move splunk folder to /opt
sudo mv splunk /opt/

4 - Start Splunk:
/opt/splunk/bin/splunk start

Afterwards, in order to stop it:
/opt/splunk/bin/splunk stop

5 - Accept the license:
type q to skip reading and y to accept

6 - Register an username and password (eg: admin / admin123)

7 - Access http://127.0.0.1:8000 in the browser and use the previously registered username and password

That's it folks! You've got your Splunk up and running!
```

## Dev License
```
1 - Access this link:
https://dev.splunk.com/enterprise/dev_license/

2 - Click on: "Go to the Splunk Developer Agreement page."

3 - Agree and submit it in order to request the license

4 - Once you have received the license by email, hit http://127.0.0.1:8000 (your local Splunk) and go to Settings > Licensing

5 - Click on "Add license", choose the file received and click on the button "Install"
```

## Basic Searching & Syntax
```
POST index="splunk_training" action=addtocart uri="/cart*"
index="splunk_training"
index="splunk_training" | stats count by status
index="splunk_training" | stats avg(bytes)
index="splunk_training" | stats dc(categoryId)
index="splunk_training" | timechart span=1h count(itemId) by source
index="splunk_training" | timechart span=1h avg(bytes) by source
index="splunk_training" action="purchase" | stats count by productId
index="splunk_training" action="purchase" productId=* | timechart count by productId limit=20

How to use variables in Dashboard (surround the variable name with dollar signs):
index="splunk_training" action="purchase" productId=$product$ | stats count by productId
index="splunk_training" action="purchase" productId=$product$ | timechart count by productId limit=20

Search String / SPL query to be used in Dashboard Dropdown:
index=splunk_training | dedup productId | fields productId

index="splunk_training" ERROR
index="splunk_training" /cart/ERROR

CSV Lookups
| inputlookup http-status
index="splunk_training" status=* | lookup http-status Code as status OUTPUT Message as status_text | search Message !="OK" | table _raw, status_text, status
```
