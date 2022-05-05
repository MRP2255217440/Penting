Hello, welcome to Penting!

After you download this folder, you must decompress the folder.

Once done you then need to open the .ovf file using a VM tool.

For VMware, you need to select 'open a virtual machine' and then select the .ovf file.

Although the tool should still work with Virtual Box, Penting was designed to work with VMware.

By default, Penting will be set to NAT, meaning it can access the internet. If you do not want this, change it to Host.
NB: Whilst Penting is set to Host it will not be able to attack Bad Store

Login details for Penting are: dmu:dmu

The rest of this text file is content accessible from the Penting desktop.


----------------------------------------------------------------------------------------------------------------------------------



Note - it is best to run the apt-get update and upgrade command every now and then to ensure all programs are the newest versions. sudo apt-get update && sudo apt-get upgrade

THE SUPER USER PASSWORD IS root

The guide website can be found via localhost:1001




----------------------------------------------------------------------------------------------------------------------------------




Tools - Below are a list of tools and how to access the help page:
curl - curl -h
wget -h
nmap - nmap -h
zenmap - sudo zenmap
Burp Suite - Use the GUI shortcut or:java -jar /home/dmu/BurpSuiteCommunity/burpsuite_community.jar
nikto 2.1.5- nikto -h
nikto 2.1.6- '/home/dmu/nikto/program/nikto.pl -h', or alteranively go to /home/dmu/nikto/program and then just enter './nikto.pl -h'. if this does not work, 'perl nikto.pl -h' should also work
metasploit - msfconsole. Although this tool was not covered in the guide, I recommend taking a look at it

s

----------------------------------------------------------------------------------------------------------------------------------



Services:
DVWA - website can be found somewhere on localhost
BadStore - website can be found from investigating the other VM found alongside Penting. Make sure it is turned on first
Mutillidae - website can be found on port 80 when it is run - see below for steps to set it up

Although Mutillidae has been provided, you cannot run Mutillidae and DVWA at the same time. 
As such Mutillidae will need to run first stop the Apache2 server to run Mutillidae.
Setting up Mutillidae will wipe the DVWA database and may require reconfiguration,  as such this should only be done if you wish to do bonus content with Mutillidae (my DVWA was comlpetely unaffected, so your experience may vary)

A backup is recommended

Steps to setup Mutillidae:
1) On the console, login as root user by entering 'su'. The password is 'root'
2)Once done, stop the Apache2 service with the following command: sudo service apache2 stop
3)Then proceed to the docker location of Mutillidae - 'cd /home/dmu/Docker/mutillidae-docker'
4)Once within the area, enter 'docker-compose up' to start the docker service. This will start the Mutillidae, which can now be accessed on localhost:80
5)click the 'click here' highlighted text to make the database
6)And that should be it!

If you wish to setup DVWA again, restart the Penting VM and return to the DVWA setup page and recreate the database

