# STAGE 3:
In stage 3 I split out the database functionality from the EC2 instance .. running MariaDB to an RDS instance running the MySQL Engine.
This will allow the DB and Instance to scale independently, and will allow the data to be secure past the lifetime of the EC2 instance.

# Steps:
- Create RDS Subnet Group
- Create RDS Instance
- Migrate WordPress data from MariaDB to RDS
- Stop the MariaDB Service
- Update the LT so it doesnt install

# At stage 3, we still have a lot of limitations:


- The application and database are built manually, taking time and not allowing automation FIXED

- ^^ it was slow and annoying ... that was the intention. FIXED

- The database and application are on the same instance, neither can scale without the other FIXED

- The database of the application is on an instance, scaling IN/OUT risks this media FIXED

- The application media and UI store is local to an instance, scaling IN/OUT risks this media

- Customer Connections are to an instance directly ... no health checks/auto healing

- The IP of the instance is hardcoded into the database ....

  # Architecture as of now:
  ![image](https://github.com/user-attachments/assets/ca5deb8c-4ceb-4740-966f-a30c76b368e9)

