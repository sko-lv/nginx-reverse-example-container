Nginx reverse-proxy example configuration.
===================================================

=Prerequisites:
---------------
Docker host (v.17+ )
docer-compose (v.1.19+ )

=Short description:
-------------------
Mini project consists from 3 containers:
Back-end containers:
- nginx
- apache
Front-end reverse proxy server based on nginx in container:
- reverseproxy

  The reverse proxy redirects all requests on 8080 port -> nginx servser (started in container "nginx")
                                              8081 port -> apache server (started in container "apache")

=Setup and run:
---------------
  - cd ./reverseproxy
  - edit proxy configuration file if needed (nginx-reverse-proxy-server.conf)   
  - build the reverseproxy container image with command:
     docker build -t reverseproxy .
  - start the servers:
     cd ..
     docker-compose up -d
  - Try in browser:
     localhost:8080 (nginx)
     localhost:8081 (apache)
  - stop containers:
     docker-compose down
     
     
