ElasticSearch
=====================================================

This specific branch of the repository is used to create the elasticsearch system that 
I am using in testing and develpoment.  

With the advent of elasticsearch 5.0 there were startup requirements that had been put
into place for times when elasticsearch was starting not bound to a loopback address. These
changes were trying to force configuration changes to take place on the docker host 
machine.  

To work around this, in my container I allow elasticsearch to still bind to the local
loopback address, but then use nginx as a reverse proxy to get the traffic through allowing
the container to work correctly.   

## Sample

This is a pretty simple container to start, there are two volumes that are used that you can
attach to if you so desire.  

1. /data - all elasticsearch data
2. /logs - logs from nginx/supervisord/elasticsearch

        docker run -it -p 9200:9200 --rm mikewright/elasticsearch

