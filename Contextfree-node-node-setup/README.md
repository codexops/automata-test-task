# **Run Automata ContextFree network full node using K8S**

# **Overview**

This is a stateful application with data, and each instance will have its own identity for the peer to peer communication. When it is up and running, it will listen on
port 9933 for HTTP requests, 9944 for Websocket requests, and 30333 for TCP peer-to-peer communication.
To install and run the stateful application, follow these steps: 

Clone the Repository: Clone the stateful application repository from Contextfree-node.


Run files: Using this command run all the files:
```
kubectl apply -f <file_name>
```
Check Configuration:
```
kubectl get all
```

if everything is working fine then go to logs.

Check Logs: Check logs for the syncing status of the chain:
```
kubectl logs <pod_name>
```
If syncing is proper then it show peers count is 2 or more and block hashes.
