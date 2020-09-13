# TICK Stack Dashboard 

> Building  a dashboard using the TICK Stack 

* Telegraf
* InfluxDB
* Chronograf
* Kapacitor 

Arch: 

![Archtucture](./Images/Structure.png)


![Dashboard](./Images/Dashboard.png)



Getting Started : 

---
### Default Ports: 

* Telegraf `does not expose ports by default. It will not expose ports unless you have a service plugin enabled`
* InfluxDB `:8086`
* Chronograf `:8888`
* Kapacitor `:9092`

```bash
Telegraf can also collect metrics via the following service plugins:

CPU, DISk, MEM (Default Example)
http_listener
kafka_consumer
mqtt_consumer
nats_consumer
nsq_consumer
logparser
statsd
socket_listener
tail
tcp_listener
udp_listener
webhooks
- filestack
- github
- mandrill
- rollbar
```

### Docker Images: 

* Telegraf `docker pull telegraf`
* InfluxDB `docker pull influxdb`
* Chronograf `docker pull quay.io/influxdb/chronograf:1.8.6`
* Kapacitor `docker pull kapacitor`

---
### Using Docker :

*easaier setup than downloading*

```bash
# Make sure Docker installed 
cd Docker
docker-compose build # First time only, it will pull the images and build the containers from the images.
docker-compose up #if not built, it will auto-build first then run the containers.
```

---

### Downloading :
Download Telegraf v1.15.2: 

Mac (Homebrew): 
```bash
brew update
brew install telegraf
```


Ubuntu : 
```bash
wget https://dl.influxdata.com/telegraf/releases/telegraf_1.15.3-1_amd64.deb
sudo dpkg -i telegraf_1.15.3-1_amd64.deb
```

Windows 64: 
```bash
wget https://dl.influxdata.com/telegraf/releases/telegraf-1.15.3_windows_amd64.zip
unzip telegraf-1.15.3_windows_amd64.zip
```

Linux Binaries 64
```bash
wget https://dl.influxdata.com/telegraf/releases/telegraf-1.15.3_linux_amd64.tar.gz
tar xf telegraf-1.15.3_linux_amd64.tar.gz
```
before starting telegraf on windows add to the system variables where telegraf is installes, then
start Telegraf : 

```bash
telegraf
```

---
Download InfluxDB v1.8.2: 

Mac (Homebrew): 
```bash
brew update
brew install influxdb
```

Mac OS X: 
```bash
https://dl.influxdata.com/influxdb/releases/influxdb-1.8.2_darwin_amd64.tar.gz
tar zxvf influxdb-1.8.2_darwin_amd64.tar.gz
```

Ubuntu : 
```bash
wget https://dl.influxdata.com/influxdb/releases/influxdb_1.8.2_amd64.deb
sudo dpkg -i influxdb_1.8.2_amd64.deb
```

Windows 64: 
```bash
https://dl.influxdata.com/influxdb/releases/influxdb-1.8.2_windows_amd64.zip
unzip influxdb-1.8.2_windows_amd64.zip
```

Linux Binaries 64
```bash
wget https://dl.influxdata.com/influxdb/releases/influxdb-1.8.2_linux_amd64.tar.gz
tar xvfz influxdb-1.8.2_linux_amd64.tar.gz
```
before starting InfluxDB on windows add to the system variables where InfluxDB is installes, then
start InfluxDB : 

```bash
influxd #will start the service for influx
```


---
Download Chronograf v1.8.6: 

Mac (Homebrew): 
```bash
brew update
brew install chronograf
```

Mac OS X: 
```bash
https://dl.influxdata.com/chronograf/releases/chronograf-1.8.6_darwin_amd64.tar.gz
tar zxvf chronograf-1.8.6_darwin_amd64.tar.gz
```

Ubuntu : 
```bash
wget https://dl.influxdata.com/chronograf/releases/chronograf_1.8.6_amd64.deb
sudo dpkg -i chronograf_1.8.6_amd64.deb
```

Windows 64: 
```bash
https://dl.influxdata.com/chronograf/releases/chronograf-1.8.6_windows_amd64.zip
unzip chronograf-1.8.6_windows_amd64.zip
```

Linux Binaries 64
```bash
wget https://dl.influxdata.com/chronograf/releases/chronograf-1.8.6_linux_amd64.tar.gz
tar xvfz chronograf-1.8.6_linux_amd64.tar.gz
```
before starting Chronograf on windows add to the system variables where Chronograf is installes, then
start Chronograf : 

```bash
chronograf 
```


---
Download Kapacitor v1.5.6: 

Mac (Homebrew): 
```bash
brew update
brew install kapacitor
```

Ubuntu : 
```bash
wget https://dl.influxdata.com/kapacitor/releases/kapacitor_1.5.6-1_amd64.deb
sudo dpkg -i kapacitor_1.5.6-1_amd64.deb
```

Windows 64: 
```bash
wget https://dl.influxdata.com/kapacitor/releases/kapacitor-1.5.6_windows_amd64.zip -UseBasicParsing -OutFile kapacitor-1.5.6_windows_amd64.zip
Expand-Archive  .\kapacitor-1.5.6_windows_amd64.zip -DestinationPath 'C:\Program Files\kapacitor\'
```

Linux Binaries 64
```bash
https://dl.influxdata.com/kapacitor/releases/kapacitor-1.5.6_windows_amd64.zip
```
before starting Kapacitor on windows add to the system variables where Kapacitor is installes, then
start Kapacitor : 

```bash
Kapacitord # will start the Kapacitor Service 
```



Download [References](https://portal.influxdata.com/downloads/)
