
## Problem 3
First of all, make sure the monitoring system's working as expected.

Other processes consume memory:
- Make sure we don't have any other stress process to server (use process exporter or cadvisor to monitor the nginx process or nginx container if it's using exactly memory as node exporter report).

Human action:
- Tracking log to know if someone did some weird actions in the server.
- Limit permission who can acces the server.

A huge amount requests:
- Just imagine, we have implemented nginx exporter (https://github.com/nginx/nginx-prometheus-exporter) that help us reporting metrics about nginx to troubleshoot if have any weird request or have a huge amount of traffic from strange IP.
- Checking log to know if we have a huge amount of traffic that don't come from client's IP.
- We need to know when we have more clients to predict and increase nginx server resource.

Improving:
- Auto scale up or scale out our nginx server if have a large amount traffic access again.
- Auto scale node group if memory or CPU higher than 80%.
