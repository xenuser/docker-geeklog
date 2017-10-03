# docker-geeklog
Inofficiall material for spinning up Geeklog with Docker containers.

# About docker-geeklog
This is just a simple example of how Geeklog can be deployed via Docker (compose).

It is highly important to state that this is just a dev environment.

Do NOT use this repository for setting up productive geeklog instances!

This warning exists because of the following reasons:
- The compose file contens hardcoded credentials
- The compose file uses custom PHP-FPM and Apache images
- The Apache vhost name is hardcoded (geeklog.local)
- The MySQL port is exposed (using firewalling, if you don't deploy locally)
- No SSL is used; Geeklog is exposed via HTTP

The purpose of this repository is to create a Geeklog blog in a fast manner, so playing around with Geeklog is possible.
It is not ment to deploy a blog system which should be used in production.

# How to use docker-geeklog
On your Docker host, create the following directories:
```
	/geeklog/
	/geeklog/app
	/geeklog/mysql
```


Afterwards, run:
```
	docker-compose up -d
```

Example output:

~~~

WARNING: The Docker Engine you're using is running in swarm mode.
 
Compose does not use swarm mode to deploy services to multiple nodes in a swarm. All containers will be scheduled on the current node.
 
To deploy your application across the swarm, use `docker stack deploy`.
 
Creating network "geeklogsecond_default" with the default driver
Creating mariadb_geeklog ...
Creating mariadb_geeklog ... done
Creating php_geeklog ...
Creating php_geeklog ... done
Creating apache_geeklog ...
Creating apache_geeklog ... done

~~~

Geeklog will be available under the folling name: http://geeklog.local

# Contribution
Please feel free to send in pull request if you want to improve something.

I know the way this construct was built is far away from perfect; however, it is just a simple demo setup for my own private purposes.
