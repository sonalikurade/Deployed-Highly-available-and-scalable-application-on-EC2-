# Static website hosting using autoscalling group and load balancer

In this project i have hosted one website using autosacling group and loadbalancer.In this project i have used autoscalling group for scaleup and scaledown purpose.

I have attached load balancer to autoscalling group. for the load balancer i have created one security group and one target group. In target group i have configured helthcheck to check the healthy instances. 

To achive high availablity I have hosted a website in multiple region used load balancer and autoscaling group with target group.

## Step 1: Logging In to the Amazon Web Services Console
login to your AWS account using your credentials.

## step 2: create a template 
1. In the AWS Management Console search bar, enter EC2, and click the EC2 result under Services:

2. Click on launch template , in the left side below the instance

3. To start creating a new template , in the top-right, click Create launch template:

4. To create template need to the details
   * Template name
   * Template version description
   * Select the os image
   * Select Instance Type
   * Select Key Pair
5. Click on Create Security group and create new security group by entering the below details:
    - Security group name
    - Description
    - **Inbound Security Group Rules**
        - Enter Source type and CIDR Range 
6. Go inside the advance details and write User Data Script
7. After that click on create launch template.
## Step 3 : Create Target Group
1. Go inside the Load Balancer which is present left down side. Click on Target Group.

2. Click on create target Group

3. Select Instance in Choose a target type 

4. Give Name to the Target group name and IP address type

5. Click on next to save all the changes

6. Click on Create Target Group

7. Your Target Group is redy

## Step 4 Create Load Balancer
1. Go inside the Load Balancer which is present left down side. Click on Load Balancers.

2. Click on create Load Balancer

3. Select the type of Load Balancer Which you are Going to create depending on your requirement.

4. Click on Create option to create a Load Balancer 

5. Give the name for that Load Balancer. Select “Scheme” as Internet-facing for public data  

6. Select 3-4 Availability Zone For High Availability

7. Select Security Group Which we have already Created

8. Select the target group which we have created. If your Target Group is not ready then you can create here also 

9. Go Down and click on create Load Balancer

10. Load Balancer is created successfully. And Load Balancer is ready for use.

## Step 5 Create Autoscaling Group
1. Go inside the Auto Scaling  which is present left down side. Click on Auto Scaling Group.

2. Click on Create Auto Scaling Group which is present top right side of the window

3. Give the  name for auto scaling group

4. Select the launch template which we have already created. If you not created before then you can create here also.

5. Click on next

6. If you want overwrite something change something that you can do here

7. Select the availability Zone and click on next

8. Select an option that is Attach to an existing load balancer. Because we have created a load balancer. 

9. Go down and Click on next 

10. Enter the Desire capacity, Minimum capacity and Maximum Capacity.

11. Go Down and Click on next

12. Click on next

13. Add tag option and click on next

14. Auto Scaling Group is ready

15. Go to the load balancer and copy the DNS and paste it on browser.