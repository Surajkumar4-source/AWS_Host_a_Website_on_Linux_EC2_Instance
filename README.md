
## Create an EC2 Instance and Host a Website

### Objective
To create  Ubuntu  EC2 instances, install the necessary web servers, and host websites displaying welcome messages.



### 1. Create an Ubuntu EC2 Instance and Host a Website

#### Step 1: Launch the Ubuntu EC2 Instance
1. Go to the AWS Management Console.
2. Navigate to EC2 and click on **Launch Instance**.
3. Choose **Ubuntu Server** (e.g., Ubuntu 20.04 LTS).
4. Select an instance type (e.g., t2.micro for the free tier).
5. Configure security groups to allow:
   - HTTP (port 80)
   - SSH (port 22)
6. Review and launch the instance. Download the `.pem` key file if prompted.

#### Step 2: Connect to the Ubuntu Instance
1. Open a terminal on your local machine.
2. Use SSH to connect to your EC2 instance:
   ```bash
   ssh -i "your-key.pem" ubuntu@<public_ip_of_your_instance>
#### Step 3: Install Apache Web Server
- *Update the package manager and install Apache:*
```bash

sudo apt update
sudo apt install apache2 -y
```
- *Start and enable Apache:*
```bash

sudo systemctl start apache2
sudo systemctl enable apache2
```
### Step 4: Create the Web Page
- *Navigate to Apache's default web directory:*
```bash

cd /var/www/html
```
- *Create an index.html file:*
```bash

sudo nano index.html
```
- *Add the following HTML code:*
```bash
<html>
  <body>
    <h1>Welcome to Cloud computing</h1>
  </body>
</html>
```
- *Save and exit the file.*
  
#### Step 5: Verify the Website
*In your browser, go to:*

```bash
http://<public_ip_of_your_instance>
```
*You should see the message: "Welcome to Cloud computing".*
