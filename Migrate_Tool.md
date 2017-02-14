### Use Migrate Tool for export tar.gz

1. Find a Ubuntu server.
2. Connect the Ubuntu server use *MobaXterm* , I downloaded the Free version from [download](http://mobaxterm.mobatek.net/download.html).
    + Open MobaXterm.
    + Select **Session**.
    + In the Session settings, select **SSH**.
    + In the Remote host, type the DNS Name.
    + Select *Advanced SSH Settings*.
    + Check **Use private key**, and select your .ppk file.
    + Select **OK**. 
    + Open **Sessions** window.
    + Right-click on the machine, then select *Connect as...*.
    + Type *azureuser*.
3. Log in to the server with private key.
4. `cd /tmp` to enter the tmp folder.
5. `mkdir tars` to create a new folder - "tars" under tmp.
6. Drag your tar.gz files into *tars* folder.
7. Install Migrate Tool from gitHub.  
    `git clone https://github.com/ms-hukoyun/openedx.git`  
    `cd course-migrate`  
    `chmod +x migrate-course.py`  
    `sudo apt-get install -y python-pip`  
    `sudo pip install --upgrade pip`  
    `sudo pip install bs4`  
    `sudo pip install lxml`  
    `./migrate-course.py`  
15. Run following command each time to migrate the tar.gz.  
    `./migrate-course.py -s /tmp/tars/ -f, -i, -t dog -v, > migrate.log`
