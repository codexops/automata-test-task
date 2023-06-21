
# Fix Network Issue in Docker Image

## Task
Docker Image “atactr/devops-assignment:1.0.0” (https://hub.docker.com/r/atactr/devops-assignment/tags) is having some network issues. Fix the network issue. Stimulate the issue by running the commands below and you will never get the response:

--> docker run -it --privileged atactr/devops-assignment:1.0.0 

--> curl -v www.google.com


## Solution
This docker image "atactr/devops-assignment:1.0.0" is based on Centos 7 image. 

Steps to solve the issue:

- Check ip table
      
      iptables -L (Command for show ip table)
      
      Output:-

      Chain INPUT (policy ACCEPT)
      target     prot opt source               destination         

      Chain FORWARD (policy ACCEPT)
      target     prot opt source               destination         

      Chain OUTPUT (policy ACCEPT)
      target     prot opt source               destination         
      DROP       tcp  --  anywhere             anywhere             tcp dpt:http
- Remove Output rule 
      
      iptables -D OUTPUT 1 (Command for remove ip rule serial no.1)


- Check ip table again
      
      iptables -L (Command for show ip table)
      
      Output:-

      Chain INPUT (policy ACCEPT)
      target     prot opt source               destination         

      Chain FORWARD (policy ACCEPT)
      target     prot opt source               destination         

      Chain OUTPUT (policy ACCEPT)
      target     prot opt source               destination   


  Now we can use "curl -v www.google.com"      


