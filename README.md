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
  
