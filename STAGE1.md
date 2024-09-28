
# Stage 1:

In stage 1 of this project :

- Setup the environment which WordPress will run from.
- Configure some SSM Parameters which the manual and automatic stages of this advanced demo series will use
- And perform a manual install of wordpress and a database on the same EC2 instance.

# Steps :
- STAGE 1A - Login to an AWS Account
- STAGE 1B - Create an EC2 Instance to run wordpress
- STAGE 1B - Create SSM Parameter Store values for wordpress
- STAGE 1C - Connect to the instance and install a database and wordpress
- 
    
# Parameters created:
- Create Parameter - DBUser (the login for the specific wordpress DB)

- Create Parameter - DBName (the name of the wordpress database)
- Create Parameter - DBEndpoint (the endpoint for the wordpress DB .. )
- Create Parameter - DBPassword (the password for the DBUser)
- Create Parameter - DBRootPassword (the password for the database root user, used for self-managed admin)

# This configuration has several limitations :-

- The application and database are built manually, taking time and not allowing automation
- It was slow and annoying ... that was the intention.
- The database and application are on the same instance, neither can scale without the other
- The database of the application is on an instance, scaling IN/OUT risks this media
- The application media and UI store is local to an instance, scaling IN/OUT risks this media
- Customer Connections are to an instance directly  no health checks/auto healing
- The IP of the instance is hardcoded into the database
  
# Architecture at Stage 1
  ![image](https://github.com/user-attachments/assets/7263f6c9-a75e-4662-abc2-65ed2c4016b5)
