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
FLUSH PRIVILEGES;
````
#### Install WordPress in EC2 Instance: 
Download WordPress: 
````
wget https://wordpress.org/latest.tar.gz
````
````
tar -xvf latest.tar.gz
````
<img width="373" alt="image" src="https://github.com/user-attachments/assets/2b21bf5f-eef0-471e-bb26-473c8b857c34" />

then Move the WordPress files to the Apache root directory
````
mv wordpress/ /var/www/html/
````
<img width="373" alt="image" src="https://github.com/user-attachments/assets/a5ff4d50-3542-4dbe-b4d1-40ad49a9c98e" />

Set appropriate permissions: 
````
chown -R www-data:www-data /var/www/html/
````
<img width="373" alt="image" src="https://github.com/user-attachments/assets/5e7c19b9-84f1-4124-8e0e-2b2461e89882" />

Rename the sample configuration file
````
mv /var/www/html/wordpress/wp-config-sample.php /var/www/html/wordpress/wp-config.php
````
<img width="372" alt="image" src="https://github.com/user-attachments/assets/82199c5f-8c20-4797-98d0-bce143f26796" />

<img width="374" alt="image" src="https://github.com/user-attachments/assets/4892ba27-2138-40db-8666-8e2d011c9173" />
````
vim /var/www/html/wordpress/wp-config.php
````
<img width="374" alt="image" src="https://github.com/user-attachments/assets/71443269-47be-4a48-8943-9b572956c143" />

#### Edit the configuration file: 
Enter your MySQL database details (database name, username, password).
<img width="374" alt="image" src="https://github.com/user-attachments/assets/f4d6e467-c220-4328-a2a5-fbff05460035" />

#### Restart the Apache web server to apply the changes. 

````
systemctl restart apache2
````

#### Complete WordPress Installation: 
Open your web browser and navigate to your server's IP address or domain name. Follow the on-screen instructions to complete the WordPress installation by providing site information, creating an admin account, and so on.  

- HIT PUBLIC IP of Instance

````
http://<public ip of ec2 instance>/wordpress/
````

<img width="470" alt="image" src="https://github.com/user-attachments/assets/2522e6e7-48b7-48f2-9717-ec8cef33387e" />

#### Create user 
Fill all the details to create wordpress user.

<img width="465" alt="image" src="https://github.com/user-attachments/assets/d29fd1e7-3807-479c-93a2-0b167761c429" />


<img width="469" alt="image" src="https://github.com/user-attachments/assets/7404417a-ffa0-4bec-8514-27dc71d85db9" />

#### Sample of created user: 


<img width="468" alt="image" src="https://github.com/user-attachments/assets/0f90e079-0685-48a8-93d5-4d0959a7a747" />

#### Creation of blog By logging into wordpress you can create blog.


<img width="468" alt="image" src="https://github.com/user-attachments/assets/1c290577-c950-4bf5-9333-e178741f7a1d" />


<img width="467" alt="image" src="https://github.com/user-attachments/assets/e01d9562-1878-4caf-8192-ec6444012843" />



