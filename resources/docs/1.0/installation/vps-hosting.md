# Installation the script on VPS hosting
---
### Getting Started

The first thing we will need is a Public VPS Server to host our PHP web application on.

I will be using  Digital Ocean  to Get a VPS Server

 Digital Ocean  has already Configured Servers (LAMP) For hosting which makes it a lot easier as you will see later, so we don’t need to install Apache, MySQL, PHP, or anything else.

So Just Signup and Create a VPS Droplet Machine and be sure to Select Lamp Server as your Server System.

---

#### **Reset Droplet Password**

After you create the Droplet, you will receive an email containing the root default password.

Simply connect to your Droplet using [Putty SSH Client](https://www.putty.org/) and Reset the password.

---

#### **Upload PHP Files to Your Server**

Connect to Your VPS Server using [WinSCP,](https://winscp.net/eng/download.php) and Update the PHP Files to the server to this path: “/var/www/html”

In my case, I have a Zipped file, so I need to extract it. So again to Putty SSH CLient and Let’s install the unzip utility using the following command:

---
sudo apt-get install unzip

Clear putty screen to make in clean using the following command:

---

clear

Change directory to /var/www/html using the following command:

---

cd /var/www/html

Unzip the “.zip” file using the following command:

`unzip main.zip`

*Note: the file name may be different in your case, so replace _main_ with your file name.

Now, Move the latest folder content to the upper directory so it can be accessed directly -> use WinSCP  
Just Drag and Drop using WinSCP  
Then delete the html folder, and rename “_main_” to html.  
In this way, the Your PHP files are in the html folder directly, so it can be accessed directly using your domain name.

---

#### **Start Installation**

Now you can open your browser, and enter the Droplet IP and You will see the application startup page.

---
#### **Install PHP modules**

Open Putty, and run the following commands to install PHP Modules:

`sudo apt install php-curl`  
`sudo apt install php-mbstring`

*Restart apache service using the following command:

`sudo service apache2 restart`

---

#### **Create the Database**

1- Open Putty SSH Client and run the following command:

 `mysql -u root -p`

Login to MySQL with your root password

2- Create the database using the following command:

`CREATE DATABASE _xero_;`

3- Create a new user if root has not local accessible

`CREATE USER ‘xero’@’localhost’ IDENTIFIED BY ‘Xero_db_pass123’;`

`GRANT ALL PRIVILEGES ON * . * TO ‘xero’@’localhost’;`

`FLUSH PRIVILEGES;`


---

#### **Setup cronjobs**

Open WinSCP and got to /etc  
Open **crontab** file using the editor  
And paste all the jobs from Xerochat ( or your application) as explained in the video.

Now, the last step is to point your domain name to your IP address in the DNS management zone.


----

#### **Finish**
You will go to your site domain _/install_ to complete installation wizard 