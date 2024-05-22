
## Open Git Bash and Connect to the EC2 instance using SSH command

## Create Splunk user
```bash
sudo adduser splunk
```
## Create directory "splunk"
```bash
sudo mkdir /opt/splunk
```
## change the ownership of the directory to Splunk user
```bash
sudo chown -R splunk:splunk /opt/splunk/
```
## Check if the Ownership is changed to splunk
```bash
ll /opt/splunk/
```
## Install wget
```bash
sudo apt install wget
```

## Switch to splunk user
```bash
sudo su splunk
```

## Navigate to splunk user home directory
```bash
cd /home/splunk
```
## Download the Splunk Enterprise (Based on the version you want, you can get this command from https://www.splunk.com/en_us/download/splunk-enterprise.html) 
```bash
wget -O splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz "https://download.splunk.com/products/splunk/releases/9.2.1/linux/splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz"
```
## Extract the tar package
```bash
tar -xvf splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz -C /opt/
```
## Navigate to Splunk bin directory
```bash
cd /opt/splunk/bin
```
## Start the Splunk with accepting license
```bash
./splunk start --accept-license  --no-prompt --answer-yes --seed-passwd Pa55word
```
## Exit from the splunk user
```bash
exit
```
## Stop the Splunk and enable the boot start
```bash
sudo /opt/splunk/bin/splunk stop
sudo /opt/splunk/bin/splunk enable boot-start -user splunk
```
## Start the Splunk
```bash
sudo /opt/splunk/bin/splunk start
```

