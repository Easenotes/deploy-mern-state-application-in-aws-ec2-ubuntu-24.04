# Deploy a MERN Application to AWS EC2 Instance (Ubuntu 24.04)

Learn how to deploy a MERN stack application to an AWS EC2 instance and set up a production-ready web server for your MERN application on Ubuntu 24.04.

This guide explains how to create a fully functional MERN stack web application on an Amazon EC2 instance (Elastic Compute Cloud) and deploy a customized MERN stack application that supports user registration and authentication.

## Steps to Deploy the MERN Application on Ubuntu 24.04

### 1. Launch a New Ubuntu Server on AWS EC2
- Sign in to your AWS account.
- Navigate to the EC2 dashboard.
- Click on "Launch Instance" and select Ubuntu 24.04 as your Amazon Machine Image (AMI).
- Configure instance details, security groups, and storage settings as needed.
- Launch the instance and wait for it to initialize.

### 2. Connect to the Ubuntu EC2 Instance via SSH
- Open a terminal (or Git Bash) on your local machine.
- Set the permissions for your private key file:
    ```bash
    chmod 400 <path-to-key-file>
    ```
- Connect to your EC2 instance using the following command:
    ```bash
    ssh -i <path-to-key-file> ubuntu@<public-dns>
    ```

### 3. Clone Projects under the Ubuntu OS in Amazon EC2
- Install Git if it’s not already installed:
    ```bash
    sudo apt update
    sudo apt install git
    ```
- Clone your MERN stack project repository:
    ```bash
    git clone <repository-url>
    cd <project-directory>
    ```

### 4. Set Up a Server with Node.js and MongoDB
- Install Node.js:
    ```bash
    curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
    sudo apt install -y nodejs
    ```
- Install MongoDB:
    ```bash
    sudo apt install -y mongodb
    ```
- Start MongoDB:
    ```bash
    sudo systemctl start mongodb
    ```

### 5. Set Up and Install All Packages in the Clone Project
- Navigate to your project directory and install dependencies:
    ```bash
    npm install
    ```

### 6. Change the Proxy Server in `server.js`
- Update the proxy settings in your `server.js` file to match your environment.

### 7. Install PM2 and Run the Application
- Install PM2:
    ```bash
    sudo npm install -g pm2
    ```
- Start your application using PM2:
    ```bash
    pm2 start server.js
    ```
- To run the client, navigate to the client directory and use:
    ```bash
    pm2 start client.js
    ```

### 8. Test the MERN Stack App in a Browser
- Open a web browser and navigate to your EC2 instance's public IP or DNS to access the application.

## Conclusion
You have successfully deployed a MERN stack application on an AWS EC2 instance running Ubuntu 24.04. Your application should now be accessible over the web.

## Additional Resources
- AWS Documentation
- MERN Stack Documentation
- Node.js and MongoDB Documentation

Feel free to modify and expand this guide based on your specific application needs!
