#Clean Up Docker Images:
docker rm $(docker ps -qa) 
docker rmi -f $(docker images -q)  
docker volume prune -f

