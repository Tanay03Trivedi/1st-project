![Untitled](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/5b7a4b59-14e8-469f-9454-55535587b7ac)

- Step – 1 

create vpc with (2 private, 2 public ) subnets in different availability zones,2 Nat gateway in different availability zone,one internet gateway

- step – 2

go to auto-scaling group

 create auto-scaling group

 create launch template
 
 select os
 
 select instance type

 create a security group in the created vpc  and select it in the launch template

 select launch template

 in instance, launch options select vpc and private subnets and zones

 in the advanced option select an application load balancer – internet-facing

 in group size desired capacity 1 scaling limit 1 max desired capacity 1 no scaling
 
 policy, no instance maintenance policy

 review the configuration and create auto scaling group

- step - 3

 create 2 instances as a bastion host
 
- step - 4

connect the private IP host and deploy webserver

 - step -5

 register the private subnet instance in the load balancer
 
 - step – 6
 
 copy dns name and test for replay from both web server





                                       Step -1 VPC configuration

- 2 Availability zone
- 2 public subnets
- 2 private subnets
- 1 NAT gateway per availability zone
- 1 Internet gateway                                      
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/82633785-bd2f-4ba3-b07b-b0d5d803cb6c)
                                      The Routes will be as shown below
  - 1a public -> rtb-public -> Internet gateway
  - 1a private -> rtb-private-1a -> nat-gateway-1a
  - 1b public -> rtb-public -> Internet gateway
  - 1b private -> rtb-private-1b -> nat-gateway-1b
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/159f4ea2-3921-410d-b2fc-7fda021123d2)

                                      create auto-scaling group
 - create a launch template
 - need a security group for that
 - select the operating system
 - select the instance type   
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/d84847f9-4b41-4088-adc0-8fbca74f1604)

                                     launch options
   - select the project vpc and 2 private subnets (private-1a,private-1b)

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/bd6062de-7089-4ac2-880d-81bc0549ea00)

                                     A new load balancer
   - internet-facing
   - project vpc
   - 2 public subnets
                                  
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/5bdaa519-d5f0-459b-8e4c-fc872ae117e6)

                                      Group size
- can change after also
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/5ff62dd5-3aa9-4176-87e0-5eb5c371dcff)

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/7a535c27-67c4-4c7d-9ef2-ddb877374f01)

                                      

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/ba239962-f603-40fe-89ae-178c58fa92bc)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/61099dd3-bef7-4d2c-bb24-4d6da1c56893)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/1e1e5dfd-ef79-464e-9d51-88ae1d70cbdb)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/837d5639-7010-4ba4-80a1-586ec9d3bd71)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/f29b3247-50a2-4c29-9b33-405137a7789f)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/17b6d301-0e09-45f1-8b32-2da7be5cd20d)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/05e26778-6939-4149-a68c-a2dcb7dcbffb)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/ed2284fd-f0b3-4d3f-a13f-b0425cbfc1c1)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/446fe9f2-c3d1-4d83-83a1-c07a5b777fef)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/35b3b88e-52dc-48ef-bd58-2becea91b1ae)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/0c5e6f2f-195f-4051-9124-cf337c3b21ee)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/c02da625-cf9e-46fd-b45e-b38924cd3922)

