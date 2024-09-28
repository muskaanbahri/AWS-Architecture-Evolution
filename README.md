# AWS-Architecture-Evolution Overview: 
This project demonstrates the deployment of WordPress on AWS using an automated and scalable architecture. By progressively improving the setup, the final solution includes automated deployments, independent scaling for the application and database, persistent media storage, and load balancing with auto-scaling.
Modernize a WordPress app. Start with a single server. Add components like database separation, CDN, autoscaling, and load balancing. Use tools for infrastructure as code, monitoring, and logging.
This project consists of 6 stages, each implementing additional components of the architecture
# STAGES:
Stage 1 - Setup the environment and manually build wordpress

Stage 2 - Automate the build using a Launch Template

Stage 3 - Split out the DB into RDS and Update the LT

Stage 4 - Split out the WP filesystem into EFS and Update the LT

Stage 5 - Enable elasticity via a ASG & ALB and fix wordpress (hardcoded WPHOME)

Stage 6 - Cleanup


# Architecture
- WordPress Application: Deployed on EC2 instances using Launch Templates and Auto Scaling Groups.
- Database: Migrated from local MariaDB to an RDS instance running MySQL for independent scaling.
- Media Storage: Stored on Amazon EFS to ensure media persistence across instances.
- Load Balancer: Application Load Balancer (ALB) distributes traffic across multiple instances, ensuring high availability and auto-healing.
# Key Components
- Launch Template: Automates WordPress installation and configuration.
- RDS MySQL Database: Separates the database from the application, allowing independent scaling.
- Amazon EFS: Ensures media files are shared and persisted across instances.
- Auto Scaling Group (ASG): Scales the WordPress instances based on load.
- Application Load Balancer (ALB): Balances traffic and ensures failover and health checks.
# Features
- Automated and scalable deployment of WordPress.
- Independent scaling for the database and application.
- Persistent, shared media storage.
- Auto-healing with ALB and ASG integration.
# Limitations Addressed
- Manual setup and hardcoded configurations.
- Lack of scalability for the application and database.
- Media loss during scaling.
- No load balancing or health checks in the initial setup.
# Future Enhancements
- Use Amazon CloudFront for content delivery.
- Implement WAF for enhanced security.
- Configure Multi-AZ RDS for higher database availability.
