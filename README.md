# Java Cluster

Dockerized java environment for deployment with compose on a single node or swarm in a cluster with high availibility.

Haproxy is configuered to perform servie discovery using the docker dns server. The tomcat instances use memcache to store the session. If run as cluster via swarm, memcache can be configured with a fallback. In that case the tomcat workers will replicate their session to the fallback node to achieve high availibility for the sessions.


