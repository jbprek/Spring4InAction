HOW TO RUN
=========

Docker use
-----------
1.-Run tomcat docker image, map Tomcat port 8080 to 18080

`docker run --rm  --name tomcat8ori  -p18080:8080 tomcat:8.0`

2.- Stop the container  i.e. ^C
      
3.-Copy modified tomcat-users.xml modified file with default uses inside docker container

`docker cp ./util-files/tomcat-users.xml  tomcat8ori:/usr/local/tomcat/conf/`    
 
4.-Commit changes to a new image

`docker commit tomcat8ori jbprek/tomcat8`  

5.- Run the new container

`docker run -d --name tomcat8  -p18080:8080 jbprek/tomcat8`


6.Connect to tomcat container if needed

`docker exec -it tomcat8 bash`


     
 