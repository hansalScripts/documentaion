# Installation the script on shared hosting
---
#### **Installation with Apache**
---
##### **Creating a new Database**

First thing you want to do before installing **EasyWall** is to create a new database on your mysql server. If you already know how to do this/or have already created one just skip to the next step.

&nbsp;

Your hosting provider will most likely have **phpMyAdmin** as mysql manager. If that is the case here is a step by step guide (if not the process will be very similar on other managers).

&nbsp;

Login to your control panel, find and click phpMyAdmin link.

&nbsp;

Click on the database tab in the top menu, enter any name for your database and click create.

---

##### **Uploading Files**

After creating a database, unzip the file you downloaded and upload the **contents** of **EasyWall** folder to your server root, usually

`/path/to/www/` or 

`/path/to/html/`  or 

`/path/to/httpdocs/`  or 

`/path/to/public_html/`.

&nbsp;

**Important:** Always use a desktop application like [FileZilla](https://filezilla-project.org/) to upload files to FTP as opposed to web based file managers to avoid issues with corrupted or not properly uploaded files.

&nbsp;

**Important:** Make sure that **.htaccess** file got copied properly from the download to main MicroJob folder on your server.

---

#### **Launch the Installer**

After you created a database and uploaded the files, simply open up your site in the browser (like **http://mysite.com**, you will redirect to **http://mysite.com/install**) 
and follow on-screen instructions to complete the installation.

---
#### **Installation with Nginx**

  1. Put all the MicroJob package files to your server root, usually

`/path/to/www/` or 

`/path/to/html/` or 

`/path/to/httpdocs/` or 

`/path/to/public_html/` 

and set your server configuration like this:
`root "**/path/to/www/**public";


`location / {
try_files $uri $uri/ /index.php?$query_string;
}`

  2. Then restart Nginx.
  3. Create a MySQL database, add user to it with full permissions.
  4. Go to the script's installation URL. For example
`http://mysite.com/install`
  5. And follow the web installation wizard.
