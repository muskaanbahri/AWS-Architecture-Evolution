# STAGE 5:
In stage 5 of this advanced demo lesson, we will be adding an auto scaling group to provision and terminate instances automatically based on load on the system.

We have already performed all of the preparation steps required, by moving data storage onto RDS, media storage onto EFS and creating a launch template to automatically build the wordpress application servers.

# Steps:
- Create the load balancer
- Create a new Parameter store value with the ELB DNS name
- Update the Launch template to wordpress is updated with the ELB DNS as its home
- Create an auto scaling group (no scaling yet)
- Integrate ASG and ALB
-  Add scaling
-  SCALEOUT when CPU usage on average is above 40%
-  SCALEIN when CPU usage on average ie below 40%
-  ADJUST ASG Values
-  ADJUST ASG Values
# We have finally created an architecture which has no limitations 


- The application and database are built manually, taking time and not allowing automation **FIXED**
- ^^ it was slow and annoying ... that was the intention. **FIXED**
- The database and application are on the same instance, neither can scale without the other **FIXED**
- The database of the application is on an instance, scaling IN/OUT risks this media **FIXED**
- The application media and UI store is local to an instance, scaling IN/OUT risks this media **FIXED**
- Customer Connections are to an instance directly ... no health checks/auto healing **FIXED**
- The IP of the instance is hardcoded into the database .... **FIXED**

  # Completed Architecture:
  ![image](https://github.com/user-attachments/assets/ad3945c8-d667-4030-a0a5-fd0ff9f2738b)

