# Implementing_Loadbalancers_with_Nginx

1. Provisioning EC2 instance

To statrt the project, two (2) Ubuntu 22.04 EC2 instances were provisioned on AWS: Weberver 1 and Webserver 2.

![Provisioned EC2 instances](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/4f9971a6-d44e-40e3-84a2-e592b63dcd94)

2. Preparing Ports for Traffic and Load Balancing

On Webserver 1, an inboud rule allowing traffic on Port 8000 from anywhere was added to the security group as shown below

![Webserver 1 inbound rule modification](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/c18089cd-1c74-4364-8058-310854ac3236)

Similarly, the security inbound rule for Webserver 2 was modified to allow traffic from Port 80

![Webserver 2 inbound rule modification](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/19a1ff90-1ad4-4d3e-9900-1bfd68eeb80a)

3. Installation of Apache Webserver

