# LaravelPermission
**Your User Account as owner**
Personally, I give myself the ownership of all directories and files in my project. This makes it easier for me to work with the directories and files.

**sudo chown -R $USER:www-data /var/www/<your-project>**

Then I set all my directories to 755 and files to 644 like so:

**sudo find /var/www/<your-project> -type f -exec chmod 644 {} \;  
sudo find /var/www/<your-project> -type d -exec chmod 755 {} \;**

Then I give the web server the permissions to read and write to the storage and bootstrap/cache directories as required by Laravel.

In your project root:

**sudo chgrp -R www-data storage bootstrap/cache
sudo chmod -R ug+rwx storage bootstrap/cache**

With this, you are secure and your website will work fine without any permission issues. Working with files also does not give you any issue.
