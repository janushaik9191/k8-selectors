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
```````````````````````````````````
    affinity(node and pod)

        node affinity is two types
    1 . requried during scheduling (need to satisfy the taint condition)
    2 . prefferd during scheduling (tries for the defined condition if not found schedule in   any another availabe node)
        pod affinity
    1 . first one pod is scheduled in a node
    2 . second pod is also scheduled into a same node based on label condition
    3 . third node is scheduled in a different node by using anti affinity definition
``````````````````````````
popular use case for affinity and anti affinity with cache(pod) and pods

Ref: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/