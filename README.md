# INSTALLING 
## Before install :
## Unpacking Joomla + VirtueMart 
0. `cd public_html/ && unzip VirtueMart.zip && rm VirtueMart.zip`
    `scp -r VirtueMart3/* ./ && rm -rf VirtueMart3`
### Installing docker images
1. `docker-compose build`
2. `docker-compose up`
## Adding database
3. Insert URL in the browser : `http://localhost:8765`
4. Accesses : <br>{<br>
    login : root<br>
    password : qwerty<br>
}<br>
5. Add a new database and remember the <b>name</b>
## Installing
### Joomla
6. Insert URL in the browser : `http://localhost:8080`
7. Fill the configuration page.
8. Save admin username, password to access.txt file.
9. Click next.
10. To find database host, insert `docker inspect {docker_mariadb_image}`
- where docker_mariadb_image name of your docker mariadb image 
- find the IPAddress field, like 172.19.0.3
11. Insert database information : <br>{<br>
    host : {docker_mariadb_image}<br>
    user : root<br>
    password : qwerty<br>
    name : from a previous step<br>
}<br>
12. Click next.
13. If Hikashop ask to delete the file - delete to confirm that you are the owner of the site.
14. Click next and wait until database installing.
15. Select demodata for store.
16. Click install.
17. `rm -rf public_html/installation`.
18. Click go to the control panel after installation.
19. Click Install VirtueMart.
### EMS Plugin
20. `git clone https://github.com/emspay/ems-online-virtuemart`.
21. Extension -> Manage -> Install.
22. Select Zip archieve `ems-online-virtuemart/pkg_emspay.zip`.
22. `rm -rf ems-online-virtuemart`.
23. `cd public_html/libraries/emspay && composer install`
## After install

# Now Joomla with VirtueMart installing is completed with the latest EMS Pay plugin onboard!