![Untitled](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/5b7a4b59-14e8-469f-9454-55535587b7ac)

- Step – 1 

create vpc with (2 private , 2 public ) subnets in different availability zones ,2 Nat gateway in different availability zone ,one internet gateway

- step – 2

go to auto scaling group

 create auto scaling group

 create launch template
 
 select os
 
 select instance type

 create security group in created vpc  and select in launch template

 select launch template

 in instance launch options select vpc and private subnets and zones

 in advanced option select a application load balancer – internet facing

 in group size desired capacity 1 scaling limit 1 max desired capacity 1 no scaling
 
 policy ,no instance maintenance policy

 review the configuration and create auto scaling group

- step - 3

 create 2 instance as bastion host
- step - 4

connect the private ip host and deploy webserver
 - step -5

 register the private subnet instance in load balancer
 - step – 6
 
 copy dns name and test for replay from both webserver





                                       Step -1 VPC configuration
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/ba508f46-dfc6-4115-b56f-2eb753fb798a)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/f253d28f-ef6a-4e16-af5e-2efac26ea85d)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/edde81c7-4ed4-49fe-97ca-a9cbfb6792dd)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/657d9a3b-7927-41f6-8fd7-c1ed749fb806)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/d2c5edbd-a152-4cab-8aea-e2609242fbd4)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/265b688e-6236-466b-8326-c9600377fdeb)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/a48189f9-45a4-4638-b576-375b628c3188)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/cabf92bd-e605-485a-b03f-95573c5738f2)
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

