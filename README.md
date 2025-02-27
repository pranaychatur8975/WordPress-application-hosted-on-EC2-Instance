# WordPress-application-hosted-on-EC2-Instance
### Install LAMP Stack (Linux, Apache, MySQL, PHP): 
Select ubuntu AMI and launch Ec2 instance Install

<img width="468" alt="image" src="https://github.com/user-attachments/assets/23c14600-38c4-4701-8ec1-97c36f3a590c" />

````
apt update -y
````

<img width="378" alt="image" src="https://github.com/user-attachments/assets/c64d5c62-28ee-4360-aa68-b140425cf24e" />

````
apt install apache2 -y 
````

<img width="371" alt="image" src="https://github.com/user-attachments/assets/3e0d2a4a-0448-42aa-985d-859c666b8100" />

````
apt install mysql-server -y
````

<img width="375" alt="image" src="https://github.com/user-attachments/assets/ea8ba0f8-80b6-4d78-95a2-ee097bc6956d" />

````
apt install php libapache2-mod-php php-mysql -y
````

<img width="375" alt="image" src="https://github.com/user-attachments/assets/58b08203-d103-4d50-8dcb-d8b8c0915bbf" />

### Configure MySQL: 
Secure your MySQL installation: 
````
mysql_secure_installation 
````
<img width="373" alt="image" src="https://github.com/user-attachments/assets/e255fade-f82f-4805-b4cb-cb3b1cbf4278" />

### Follow the prompts to set a root password and secure your installation:

#### 
- Enter current password for root: Press return for none 
- Change Root Password: Y 
- New Password: Enter your new password 
- Remove anonymous user: Y 
- Disallow root login remotely: Y 
- Remove test database and access to it: Y 
- Reload privilege tables now: Y
  
<img width="373" alt="image" src="https://github.com/user-attachments/assets/e0cd2f00-9beb-48ab-896f-0641449c6a7d" />

#### To get started, log into MySQL’s root (administrative) account by issuing this command: 
You will be prompted for the password that you set for the root account when you installed MySQL. Once that password is submitted, you will be given a MySQL command prompt. 
````
mysql -u root -p
`````
#### Create a new database that WordPress can control. You can call this whatever you would like, but I will be calling it WordPress for this example. 

Create a new MySQL user account that we will use exclusively to operate on WordPress’s new database. Creating one-function databases and accounts is a good idea, as it allows for better control of permissions and other security needs. 
TYPE BELOW COMMANDS: 
````
 CREATE DATABASE wordpress; 
````
````
CREATE USER 'wordpressuser'@localhost IDENTIFIED BY 'Testpassword@123'; 
````
GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpressuser'@localhost;
````
````
FLUSH PRIVILEGES;
````

<img width="373" alt="image" src="https://github.com/user-attachments/assets/dc788a5a-6676-4035-ad6b-55128e114ff5" />

#### Install WordPress in EC2 Instance: 
Download WordPress: 








