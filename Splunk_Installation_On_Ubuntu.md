## Creating user
```bash
sudo adduser splunk
sudo mkdir /opt/splunk
sudo chown -R splunk:splunk /opt/splunk/
ll /opt/splunk/
sudo apt install wget

```

## Switch to splunk user
```bash
sudo su splunk

```

## Download and Install the Splunk Enetrprise
```bash
cd /home/splunk
wget -O splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz "https://download.splunk.com/products/splunk/releases/9.2.1/linux/splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz"
tar -xvf splunk-9.2.1-78803f08aabb-Linux-x86_64.tgz -C /opt/
cd /opt/splunk/bin
./splunk start --accept-license  --no-prompt --answer-yes --seed-passwd Pa55word
exit

```

## Stop the Splunk and enable the boot start
```bash

sudo /opt/splunk/bin/splunk stop
sudo /opt/splunk/bin/splunk enable boot-start -user splunk

```
