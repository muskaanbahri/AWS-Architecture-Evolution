# Stage 4:
We will be creating an EFS file system designed to store the wordpress locally stored media. This area stores any media for posts uploaded when creating the post as well as theme data. By storing this on a shared file system it means that the data can be used across all instances in a consistent way, and it lives on past the lifetime of the instance.

# Steps:
- Create EFS File System
- Add an fsid to parameter store
- Connect the file system to the EC2 instance & copy data
- Test that the wordpress app can load the media
- Update the launch template with the config to automate the EFS part

  # This still has a lot of limitations:
  
- The application and database are built manually, taking time and not allowing automation FIXED

- ^^ it was slow and annoying ... that was the intention. FIXED

- The database and application are on the same instance, neither can scale without the other FIXED

 - The database of the application is on an instance, scaling IN/OUT risks this media FIXED

- The application media and UI store is local to an instance, scaling IN/OUT risks this media FIXED

- Customer Connections are to an instance directly ... no health checks/auto healing

- The IP of the instance is hardcoded into the database ....

  # Architecture as of now:
  ![image](https://github.com/user-attachments/assets/1a4f283e-492c-421b-8e2b-ec61f99d51fe)
