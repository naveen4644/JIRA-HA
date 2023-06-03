1. Give 777 permission to shared folder /efs-jira
2. Setup First jira node  and then transfer the dbconfig.xml to other node 
3. Stop configured node  sudo service jira stop
4. Copy the following directories from the Jira local home directory to the new sharedhome directory (some of them may be empty).

     data
     plugins
     logos
     import
     export
     caches
     keys


5. In the Jira local home directory, create a cluster.properties file, with contents as follows: 
# This ID must be unique across the cluster
jira.node.id = node1
# The location of the shared home directory for all Jira nodes
jira.shared.home = /efs-jira

6. Restart jira service in all node
7. Enable stickiness in load balancer.
