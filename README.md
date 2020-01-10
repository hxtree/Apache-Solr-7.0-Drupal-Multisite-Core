# Solr Drupal MultiSite Core

This is a Solr 7.0 core customized to handle drupal multisite solr module with Solr 7.0.

The package is not maintained and was never meant to be supported. That being said, it was used in production for a couple years without issues.

Installation of Solr 7.0 was similar to following:

```
sudo apt install deault-jre-headless default-jdk
cd /tmp
wget http://mirror.reverse.net/pub/apache/lucene/solr/7.0.0/solr-7.0.0.tgz
tar xzf solr-7.0.0.tgz solr-7.0.0/bin/install_solr_service.sh --strip-components=2
ls
install_solr_sevice.sh
chmod +x install_solr_service.sh
./install_solr_service.sh solr-7.0.0.tgz 
exit
/bin/solr create -c new_core
/bin/solr -e solrcloud
su - solr -c "/opt/solr/bin/solr create -c drupal -n data_driven_schema_configs"
java -version
service solr start
systemctl status solr.service
locate java
vim /usr/lib/jvm/java-8-openjdk-amd64/jre
cat >> /etc/environment <<EOL
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
service solr start
exit
```
