---
date: 2016-11-22T09:00:00+00:00
title: Installation
---

### Redhat & Centos & Amazon Linux

>```
 cat <<EOF | sudo tee /etc/yum.repos.d/influxdb.repo
 [influxdb]
 name = InfluxDB Repository - RHEL \$releasever
 baseurl = https://repos.influxdata.com/rhel/\$releasever/\$basearch/stable
 enabled = 1
 gpgcheck = 1
 gpgkey = https://repos.influxdata.com/influxdb.key
 EOF
>```

### telegraf.conf設定

登録後、jwt tokenを表示します。

>```
[[outputs.influxdb]]
  urls = ["https://demo.i.orangesys.io/?jwt=<jwt token>"]
  database = "telegraf" # required
>```

### サービス起動

>```
 sudo yum install telegraf
 sudo service telegraf start
>```

#### CentOS 7+, RHEL 7+

>```
  sudo yum install telegraf
  sudo systemctl start telegraf
>```
