# D085 Automation and Scaling Tools

<!-- 
INTRODUCTION OF SOLUTION

Purpose:

According to management at Satellite Ads Inc. (Sad_INC), sales of satellite advertising are projected to exceed those of terrestrial advertising by a wide margin. Advertisements must be error-free for customers to positively perceive their experience, including the initial upload, data preservation, consecutive purchases, and space display. This paper aims to present a solution to Satellites Ads Inc. for the advertising demand associated with the next generation of space advertisement satellites.

Goals and Objectives:

Satellites Ads Inc. has two objectives that must be met. The first is an automatic scaling mechanism for deploying satellite clusters as need dictates. These satellite clusters are made up of four servers, each of which can manage ads for up to 300 satellites. During high demand, Satellite Ads may employ up to sixty clusters to meet ad capacity. The ability to monitor the systems and deploy elastic services to scale the number of clusters required based on demand is the second need. To produce the desired outcome, Chef and Vagrant will be used. Clusters may be built as needed during high-performance hours or when predictions suggest a need for more clusters using Chef. This enables an administrator to design an automated system for deploying clusters as needed or scaling down clusters based on platform traffic.

Scope:

The cluster metrics will be monitored by Chef and Vagrant for the following: there should always be 10 percent of the core systems accessible to meet the actual demand plus an additional 10 percent. Next, when a cluster reaches 300 satellites, a new, larger cluster is built to match the demand. In addition, at least one scaled cluster should be available at all times. When satellite demand drops, clusters will be dismantled. Finally, send a message to helpdesk@satelliteads.com if any issues arise during the establishment or deletion of clusters.

Functionality:

When clusters are required, the automated system (VirtualBox) will be configured with a Chef workstation, Recipes, and Vagrant, and traffic distribution will be handled by a load balancer. To preserve resources, or if a mistake happens during scaling events, the autoscaling group will be responsible for adding or deleting clusters as needed. The helpdesk@satelliteads.com will be notified if there is any cluster activity such as the state, activation, or deactivation. 
-->