# AWS-Architecture-Evolution
Modernize a WordPress app. Start with a single server. Add components like database separation, CDN, autoscaling, and load balancing. Use tools for infrastructure as code, monitoring, and logging.
This project consists of 6 stages, each implementing additional components of the architecture

Stage 1 - Setup the environment and manually build wordpress

Stage 2 - Automate the build using a Launch Template

Stage 3 - Split out the DB into RDS and Update the LT

Stage 4 - Split out the WP filesystem into EFS and Update the LT

Stage 5 - Enable elasticity via a ASG & ALB and fix wordpress (hardcoded WPHOME)

Stage 6 - Cleanup
