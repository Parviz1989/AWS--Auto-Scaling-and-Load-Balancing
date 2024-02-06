# AWS--Auto-Scaling-and-Load-Balancing
Set up Auto Scaling groups &amp; Configure ELB for traffic distribution


Steps for Project: Auto Scaling and Load Balancing
1. Set Up an Elastic Load Balancer (ELB)
ELB Creation: Go to the EC2 Dashboard in the AWS Management Console, navigate to the "Load Balancers" section under the "Load Balancing" menu, and click “Create Load Balancer.”
Type Selection: Choose the type of ELB (Application Load Balancer for HTTP/HTTPS traffic or Network Load Balancer for TCP, UDP, and TLS traffic) based on your needs.
Configuration: Define the load balancer name, scheme (internet-facing or internal), and listeners (the protocol and port you want the load balancer to listen on).
Network Mapping: Select the VPC and subnets where the load balancer will route traffic.
Security Settings and Groups: If you're creating an Application Load Balancer and using HTTPS, you'll need to configure security settings. Regardless of type, assign security groups that define the allowed ports and sources.
Routing: Configure a target group, which is used to route requests to one or more registered targets (like EC2 instances).
Health Checks: Set up health checks for your load balancer to ensure traffic is routed only to healthy instances.
2. Configure Auto Scaling Groups
Launch Configuration or Launch Template: Before creating an Auto Scaling group, you must create a launch configuration or launch template. This includes information such as the EC2 instance type, AMI ID, and key pair that your Auto Scaling instances will use.
Create Auto Scaling Group: Go to the EC2 Dashboard, find the “Auto Scaling Groups” section, and click “Create Auto Scaling group.”
Specify Group Details: Name your Auto Scaling group and select your launch configuration or template. Define the maximum, minimum, and desired capacity of instances.
Configure Network: Select the VPC and subnets where your instances will be created. It's recommended to select subnets in different Availability Zones for high availability.
Scaling Policies: Define scaling policies based on conditions like CPU utilization or network input/output. This determines when instances will be launched or terminated to meet demand.
Attach to Load Balancer: Ensure your Auto Scaling group knows which load balancer to use. This will allow it to register new instances with the load balancer automatically.
Testing and Verification
Test Scaling: You can test scaling policies by generating load (e.g., using a load testing tool) and observing the Auto Scaling group's response.
Monitor and Adjust: Use CloudWatch to monitor the performance and logs. Adjust your scaling policies and ELB settings based on observed performance and load patterns.
