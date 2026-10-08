# Secure Deployment of a Flask Web Application on AWS

## Project Overview
This project demonstrates the deployment of a Python Flask student registration application using AWS cloud services.

Users can register student details, including name, email, course, and a photo. Student information is stored in a MySQL database, while uploaded photos are stored in Amazon S3.

## AWS Services Used
- **Amazon EC2:** Hosts the Flask web application.
- **Amazon RDS (MySQL):** Stores student registration records.
- **Amazon S3:** Stores uploaded student photos.
- **AWS IAM Role:** Allows the EC2 application to access S3 without storing AWS access keys in the code.
- **Amazon VPC:** Provides network isolation and controls connectivity.
- **Security Groups:** Restrict access to the application server and database.

## Application Architecture
1. A user opens the Flask web application hosted on EC2.
2. The user submits student details and a photo.
3. Flask stores student information in the RDS MySQL database.
4. The uploaded photo is stored in the S3 bucket.
5. The application uses an EC2 IAM role for S3 access.
6. The RDS database is configured for private access and accepts MySQL connections from the EC2 security group.

## Technologies
- Python
- Flask
- PyMySQL
- Gunicorn
- Amazon EC2, RDS, S3, IAM, and VPC

## Configuration
Database settings and other environment-specific values should be configured through environment variables, not hard-coded in the source code.

Required database variables:
- `DB_HOST`
- `DB_PORT`
- `DB_USER`
- `DB_PASSWORD`
- `DB_NAME`

The S3 bucket is configured using `S3_BUCKET`.

Never commit passwords, AWS access keys, private SSH keys, or `.env` files to GitHub.

## Run Locally
1. Install Python and the dependencies listed in `requirements.txt`.
2. Configure the required environment variables.
3. Ensure the MySQL database and S3 permissions are configured.
4. Start the application using the project's Flask entry point.

## Security Notes
- The RDS database is not publicly accessible.
- The database security group allows MySQL traffic from the EC2 application security group.
- The EC2 instance uses an IAM role for S3 access.
- SSH access should be restricted to trusted IP addresses.
- Public S3 object access, if enabled for this demonstration, should be limited to the intended objects.

## Author
Hasna K S

## Purpose
Academic cloud computing project demonstrating deployment of a Flask application using AWS services.
