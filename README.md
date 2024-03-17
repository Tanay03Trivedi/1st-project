# VPC-Project

![vpc project](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/57dafa0a-8016-49f0-b32d-f92674e3ac2e)

# Step – 1 

### Create vpc with (2 private, 2 public ) subnets in different availability zones,2 Nat gateway in a different availability zone, one internet gateway

# step – 2

go to the auto-scaling group

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

## step - 3

create 2 instances as a bastion host
 
## step - 4

connect the private IP host and deploy webserver

## step -5

register the private subnet instance in the load balancer
 
## step – 6
 
copy dns name and test for replay from both web server



# VPC configuration

- 2 Availability zone
- 2 public subnets
- 2 private subnets
- 1 NAT gateway per availability zone
- 1 Internet gateway
                                   
![Screenshot 2024-03-18 043324](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/ffa0a3fd-fcb2-4a06-b9a8-3fb4d28eedc8)

# The Routes will be as shown below
  - 1a public -> rtb-public -> Internet gateway
  - 1a private -> rtb-private-1a -> nat-gateway-1a
  - 1b public -> rtb-public -> Internet gateway
  - 1b private -> rtb-private-1b -> nat-gateway-1b
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/159f4ea2-3921-410d-b2fc-7fda021123d2)

## Create an auto-scaling group
 - create a launch template
 - need a security group for that
 - select the operating system
 - select the instance type   
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/d84847f9-4b41-4088-adc0-8fbca74f1604)

## launch options
   - select the project vpc and 2 private subnets (private-1a,private-1b)

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/bd6062de-7089-4ac2-880d-81bc0549ea00)

## A new load balancer
   - internet-facing
   - project vpc
   - 2 public subnets
                                  
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/5bdaa519-d5f0-459b-8e4c-fc872ae117e6)

##  Group size
- can change after also
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/5ff62dd5-3aa9-4176-87e0-5eb5c371dcff)

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/7a535c27-67c4-4c7d-9ef2-ddb877374f01)

## Review page 

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/ba239962-f603-40fe-89ae-178c58fa92bc)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/61099dd3-bef7-4d2c-bb24-4d6da1c56893)

##  Wait for instance creation by auto-scaling group
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/d4d66054-48ec-46ee-8748-772cb06ae57f)
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/8907d44a-0dbb-414f-ba59-8f919aa93fae)
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/bac1e009-c902-4eb8-9b17-b96c91420408)
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/3061d36f-3542-4397-8d57-6df68adfee49)



## Create 2 bastion hosts per availability zone
                                      
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/f29b3247-50a2-4c29-9b33-405137a7789f)

# Linux commands for this project as below
sudo –I
 - apt-get update
 - nano x		#x = any name to a file
	- 	#paste the ssh key in this file 
		- #then press ctrl+o 
	- 	#enter
	-	#ctrl+x
 - ls                    		#for checking the file created is there
- chmod  x 400    	#to give read-only permission 
 - ssh –I prac-account-ssh ubantu@xxxx.xxxx.xxxx.xxxx
 - yes
		# After connection established
 - sudo –I
- apt-get update
- apt install nginx 
 - y
- service nginx status
- echo “hello from $(hostname)” > /var/www/html/index.html
- curl localhost  
	#same on the second subnet instance

![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/2549a870-2ef1-4216-9fea-50664a8e9154)
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/a1227d70-3b42-4393-a09d-9ef6f128ed06)


## Register the auto-scaling instance in the load balancer

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/4370c2f3-cf17-433c-91ec-6a086fc2af63)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/35b3b88e-52dc-48ef-bd58-2becea91b1ae)


## Copy dns name of the load balancer and search (for results)
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/281a5cd7-1226-41a7-bfb3-0a254dc2f717)
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/b1f2f119-8cac-42bf-a897-dc64f4fc7780)

![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/61aac66d-02c4-4d26-bd39-6f7770386072)
![image](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/ae3cbabb-b7da-4658-9c0a-c9ba79508129)

