# Implementing_Loadbalancers_with_Nginx

1. Provisioning EC2 instance

To statrt the project, two (2) Ubuntu 22.04 EC2 instances were provisioned on AWS: Weberver 1 and Webserver 2.

![Provisioned EC2 instances](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/4f9971a6-d44e-40e3-84a2-e592b63dcd94)

2. Preparing Ports for Traffic and Load Balancing

On Webserver 1, an inboud rule allowing traffic on Port 8000 from anywhere was added to the security group as shown below

![Webserver 1 inbound rule modification](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/c18089cd-1c74-4364-8058-310854ac3236)

Similarly, the security inbound rule for Webserver 2 was modified to allow traffic from Port 80

![Webserver 2 inbound rule modification](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/19a1ff90-1ad4-4d3e-9900-1bfd68eeb80a)

3. Installation of Apache Webserver 1

Next, the first webserver was entered into via SSH on the terminal and Apache was installed on the machine as shown in the following figure

![Apache installed successfully on Webserver 1](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/4ce10004-706f-47e7-b507-1a495a86e8e1)


4. Configuring Apace to server content on port 8000

To enable Apache server content on port 8000 the port configuration file was modified to include a listening port of 8000 as shown below

![Listen directive for port 8000 added](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/6577a2aa-7bb6-4ad9-af14-50a1369fd01d)

This was done to be consistent with the earlier set up inbound rule on Port 8000 enabled for Webserver 1. The virtualhost was also modified from 80 to 8000 for consistency

as can be seen in the diagram below

![VirtualHost modified to 8000 on Webserver 1](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/5254565f-aa4f-46e0-82ec-371a03babc02)


5. Html content creation

Having set up the preliminary work, a html file for the content was created and the file ownership was modified 
The default html was replaced with the newly created html file and Apache was restarted 
The webserver was then tested on a browser and the results showed a successful implementation of the project to this point 

![Webserver 1 running successfully ](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/489c36e1-a90a-4ba2-b3ae-099eb6676e56)

6. Installation of Nginx on Webserver 2

With the work on Webserver 1 succeffuly implemented, Webserver 2 was opened via SSH and Nginx was installed via the CLI 

This was then tested and the result obtained is shown below 

![nginx installed successfully on Webserver 2](https://github.com/oghare01/Implementing_Loadbalancers_with_Nginx/assets/141191975/774eca05-0791-4d53-b4c9-a7eab6501815)

7. Nginx configuration

