# elk

This test is compiled to test your ability to work with some portions of a stack used in PIpl. It is important for us to understand the way you are thinking and working. We will provide you enough time to learn and complete the test, even if you are not proficient enough with the areas covered by it.

Starting point: Any suitable environment which supports Docker.

Resulting point: cluster of Elastic with 4 nodes, LogStash and Kibana

MUST:

1.	Create code to deploy Docker containers from public Docker Hub repos for the following stack, but not limited to: LogStash, ElasticSearch, Kibana. done
2.	Logstash should receive the system logs from all containers into  index in ElasticSearch. done
3.	Kibana should be able to query ElasticSearch and present all indexed logs. done
         
BONUS:

1.	Deploy separate container for Cerebro and protect it with Nginx 
	# I’ve created Dockerfile without solution for protection:
	# I thoung maybe to use cetificate but i was not sure.
	# after that I’ve run docker build . -t my_build:1.0
	# then I’ve run “docker run -p  9000:9000 my_build:1.0”
2.	Curator settings to clean up Elasticsearch indexes older than 1 week.
	# I have a solution for this from https://github.com/deviantony/docker-elk/tree/master/extensions/curator
	# but my laptop always crush when I run all the containers. :(
	# Maybe too much disk I/O 
	