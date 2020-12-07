# grafana_on_chef_automate
How to install Grafana on Chef Automate Elasticsearch backend.  
  
### 1. Install the latest Grafana OSS release
  
I used Ubuntu.  
```bash
sudo apt-get install -y apt-transport-https
sudo apt-get install -y software-properties-common wget
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
```
  
Add this repository for stable releases:  
```bash
echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```
  
Add this repository if you want beta releases:  
```bash
echo "deb https://packages.grafana.com/oss/deb beta main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```
  
After you add the repository:  
```bash
sudo apt-get update
sudo apt-get install grafana
```
  
### 2. Start the Grafana server
This starts the `grafana-server` process as the grafana user, which was created during the package installation.
  
Start the server with systemd. 
To start the service and verify that the service has started:  
```bash
sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo systemctl status grafana-server
```
  
Configure the Grafana server to start at boot:
```bash
sudo systemctl enable grafana-server.service
```
  
