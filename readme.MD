use of selectors in nodes and pods
``````````````````````````````````
Taint the node
    command used for tainting the node
        kubectl taint nodes node1 key1=value1:NoSchedule
    command used for un taint the node
        kubectl taint nodes node1 key1=value1:NoSchedule-
    command used for noexecution of currently runnig pods
        kubectl taint nodes node1 key=value:NoExecute
    command used for remove noexecution option of currently runnig pods
        kubectl taint nodes node1 key=value:NoExecute-
```````````````````````````````````
    tolarance of the pods 
        by using tolarance option we may schedule the pods to the tainted node but not guarentee
```````````````````````````````````
    labeling
        by using label concept we can schedule the pods on tainted nodes with less options
    command for label the node 
        kubectl label nodes <your-node-name> hardware=gpu
        after labeling the node, node-selector should be defined in container level
        