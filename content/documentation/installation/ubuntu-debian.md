---
date: 2016-11-22T09:00:00+00:00
title: Installation
---

### Ubuntu

>```
 curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add -
 source /etc/lsb-release
 echo "deb https://repos.influxdata.com/${DISTRIB_ID,,} ${DISTRIB_CODENAME} stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
>```

### Debian

>```
 curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add -
 source /etc/os-release
 test $VERSION_ID = "7" && echo "deb https://repos.influxdata.com/debian wheezy stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
 test $VERSION_ID = "8" && echo "deb https://repos.influxdata.com/debian jessie stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
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
  sudo apt-get update && sudo apt-get install telegraf
  sudo service telegraf start
>```

#### Ubuntu 15.04+, Debian 8+

>```
  sudo apt-get update && sudo apt-get install telegraf
  sudo systemctl start telegraf
>```
