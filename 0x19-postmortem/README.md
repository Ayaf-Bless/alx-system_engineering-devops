# Load balancer 
### Issue Summary
From 7.45 AM to 9.24 AM GMT,request to all our web pages returned a 404 Error. That is, we had no access to our backend servers. 100% of our users where affected and could not access any of our product on our platforms. Following further investigation, we discovered that our load balancer had shorted out due to heavy rains that caused power outage.
### Timeline
- 7.45 AM: Power outage.
- 7.46 AM: Backup Generator kicks in.
- 8.00 AM: After servers bootup, load balancer went off
- 8.00 AM: Pager alerted teams
- 8.20 AM: Redireted requests directly to the servers
- 8.40 AM: Server restarts begin
- 9.24 AM: 100% of traffic back online
### Root Cause
At 7.45 AM, heavy rains caused power outage which caused our power box to catch fire. Since our load balancer was one of the devices that was not protected by a surge protector, it just shut off.
### Resolution and recovery
Our monitoring systems alerted our engineers at 8:00 AM GMT, and they investigated and quickly escalated the issue.
Since we had three servers and one load balancer we configered one of the servers to act as a Load balancer as we plan to acquire new servers and hardware load balancers.
At 8.40 AM we restarted the new configured load balancer and users could now access the web application.
### Corrective and Preventative Measures
These are measures taken to prevent recurrence and improve response times:
- Add load balancers to solve the issue of single point of failer
- Ensure that all electrical devices are protected using a surge protectors

