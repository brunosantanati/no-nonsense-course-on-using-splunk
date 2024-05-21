# [*NEW* A No-Nonsense Splunk Course | Getting Started Guide](https://www.udemy.com/course/no-nonsense-course-on-using-splunk/)  

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
