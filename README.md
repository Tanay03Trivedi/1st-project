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

![Screenshot 2024-04-04 152411](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/2cc37473-3611-4e37-b43a-79a546526d76)

## Create an auto-scaling group
 - create a launch template
 - need a security group for that
 - select the operating system
 - select the instance type
   
![Screenshot 2024-03-18 043401](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/e9e4aa63-1c01-48d6-9c47-f4e245c5be44)
![Screenshot 2024-03-18 043413](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/c3a32e15-ea20-4021-8e4d-13968af9a67d)
![Screenshot 2024-03-18 043431](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/5a8f1063-5bd9-4994-bb13-f22a39852af5)
![Screenshot 2024-03-18 043442](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/dedf45ff-4cb1-479e-91a7-eb6428c6a88b)
![Screenshot 2024-03-18 043451](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/400a517b-5980-4ba5-ba46-e34f418fc9e1)
![Screenshot 2024-03-18 043504](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/51ac0873-a642-460c-9d7a-bcb3b5bc1839)


## launch options
   - select the project vpc and 2 private subnets (private-1a,private-1b)

![Screenshot 2024-03-18 043521](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/8beb4b00-036b-44c6-b6a6-e4dc926b0fa2)


## A new load balancer
   - internet-facing
   - project vpc
   - 2 public subnets
                                  
![Screenshot 2024-03-18 043537](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/c7492178-4fa8-42bd-87f3-0deb950a4c7d)


##  Group size
- can change after also

![Screenshot 2024-03-18 043545](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/d7a5f97b-16bc-4ded-8310-55a1f431bce3)
![Screenshot 2024-03-18 043553](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/b154acbf-9152-4809-a90a-ae5f25796153)


## Review page 

![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/ba239962-f603-40fe-89ae-178c58fa92bc)
![image](https://github.com/Tanay03Trivedi/1st-project/assets/160705084/61099dd3-bef7-4d2c-bb24-4d6da1c56893)

##  Wait for instance creation by auto-scaling group

![Screenshot 2024-03-18 043648](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/4869b518-b5ea-4b26-8516-fce97499a00b)

![Screenshot 2024-03-18 043713](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/47dd3108-1eb6-4082-813e-55e394d2d4ee)
![Screenshot 2024-03-18 043723](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/138fe33c-730d-41a3-8f36-4a803ec685c7)
![Screenshot 2024-03-18 043732](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/c1c4df37-464b-4646-8427-c90ab2c0bf7f)


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

![Screenshot 2024-03-18 043746](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/a92e2116-9291-4312-8526-c04728bc4dcd)
![Screenshot 2024-03-18 043754](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/6e63334c-a929-467e-89c0-c05e1db2bc50)



## Copy dns name of the load balancer and search (for results)
![Screenshot 2024-03-18 043804](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/5df7ed0c-7568-4b1d-9be7-d2121bf5aa9d)
![Screenshot 2024-03-18 043815](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/9c0c49c0-3a01-4f79-b8cd-419eee37af96)
![Screenshot 2024-03-18 043828](https://github.com/Tanay03Trivedi/VPC-project/assets/160705084/95725cc0-3f19-4ab8-ac19-6b0623e22ba7)

