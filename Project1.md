## LAMP STACK IN AWS
To implement the LAMP STACK technology I follwed these steps:
. spinned up a new EC2 instance in AWS and provisioned an ubuntu server, to connect my EC2 instance I used Windows Powershell
![Screenshot 2021-09-11 194527](https://user-images.githubusercontent.com/67397926/132966249-a5dfd0c2-999a-4a52-ae89-78bc53d4d716.png)

.Installed Apache using Ubuntu’s package manager ‘apt’

Installed package update by running sudo apt update Installed apache by running command sudo apt install apache2 Verified that apache2 is running by entering command sudo systemctl status apache2 Screen shot below showing apache2 status
![Capture](https://user-images.githubusercontent.com/67397926/132966414-61578603-6af9-47c9-bede-1c7bfc3d0b30.PNG)

To request Apache HTTP Server on port 88 I ran the command  `curl http://localhost:80`
Verified that my web server is correctly installed and accessible throughport 80 I opened a new web browser and copied my Public DNS 

![Screenshot 2021-09-11 203706](https://user-images.githubusercontent.com/67397926/132966988-c0db0b94-7e05-4d56-b8a4-aac96c577d90.png)
## MYSQL INSTALLATION
I installed mysql using the command `sudo apt install mysql-server`

![Screenshot 2021-09-11 205059](https://user-images.githubusercontent.com/67397926/132967137-a66ea21d-2e31-42d2-aa9c-1e887522cfb0.png)

## INSTALLING PHP
I installed the php package, php-mysql, and a PHP module by running
To install these 3 packages at once, I ran `sudo apt install php libapache2-mod-php php-mysql`
To confirm my PHP version I ran`php -v`
![Screenshot 2021-09-11 210607](https://user-images.githubusercontent.com/67397926/132967459-f9b26054-23ef-45eb-b9d1-234ee1f9b2a9.png)

## CREATING A VIRTUAL HOST USING APACHE
I set up a new project called project Lamp
I created a new directory called project LAMP
Then, create and open a new configuration file in Apache’s sites-available directory using your preferred command-line editor. Here, we’ll be using vi or vim (They are the same by the way):

sudo vi /etc/apache2/sites-available/projectlamp.conf
This will create a new blank file. Paste in the following bare-bones configuration by hitting on i on the keyboard to enter the insert mode, and paste the 

`<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>`
