# privatevpn
This is a self hosted vpn on a ubuntu web server. Most normal Vpn providers ask for a premium for their services and you won't have no way of knowing that they won't sell your info to third parties. A self hosted vpn is cheaper and gives you the control of your data. I've illustated the steps below on how to create your own private vpn and host it for free for the first 10 months.

## Using my vpn

Download the <a href="https://openvpn.net/community-downloads/">open vpn client</a> and import the guest.ovpn file.
Click on connect. You're now connected to a vpn and have changed your IP and geolocation!



# getting  a server
The first is getting a  web server to host your vpn, i've used the digital ocean starter ubuntu server which comes @ 5$/month, but you can sign up with your <a href="https://education.github.com/packgithub">student account</a> and get 50$ digital ocean credit and host it for free.
You can also use AWS google webservices or any of other free cloud services to host it for free.

## For digital ocean

1. <u>Go to create a droplet</u>
<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img1.png">

  Select the lowest tier for 5$/month. Our vpn server doesn't require much resources so this should be more than enough to run it.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img2.png">

  Now you'll get a mail in your digital ocean registered email id with the login initials for your ubuntu server.

  It will look something like this.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img3.png">

  Now your web server is ready for you to tinker with.
  Go to your digital ocean dashboard and copy the IP address.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img4.png">

2. <u>Accessing your ubuntu webserver</u>

  Now to open the webserver, we're using putty for windows. You can use ssh on a terminal if you have a mac or gnu/linux. Go to putty     website and <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">download putty</a>
  
  Now run the installer and open putty. You'll be greeted with the login screen. Put in the IP address of the server and click open.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img5.png">

  For the first time you can enter the username as <b>root</b> and the password that you get in your mail. You don't need to copy it      all. 
  YOu can click mouse button to paste the password in the putty terminal. You'll be asked to change your default password. Enter your
  password again and create a new password.
  
  Now you're ready to go. It's good convention to update your system the first time so run the following commands:
  
  `sudo apt update -y` press enter and type your password.
  
  `sudo apt upgrade -y` and repeat
  
  Now I recommend you type `reboot` and restart your ubuntu webserver. The putty client will show connection stopped. Wait a few seconds
  and open putty again. Login in to your webserver.
  
  <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img6.png">
  <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img7.png">
  
3. <u>Setting up the vpn</u>

  Type the following commands:
  
  `wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh`
  
  <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img8.png">
  
  Run the script and follow the instructions. When it asks for a client name, you can put in anything like, desktop or phone. This 
  client allows you to make 250 different clients.
  
   <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img9.png">
   
  Now type the following command:
  
  `chmod 777 openvpn-install.sh`
  
  To create more profiles you can type `./openvpn-install.sh` and remove or add more profiles. You can also change the configuration
  if you want to but it is not recommended.
  
## Setting up the VPN clients

We will be using open vpn to access our vpn server. Download the latest open vpn client from the
<a href="https://openvpn.net/community-downloads/"> downloads page</a> or you can use
the version that i've provided.

Run the installer and install all the additonal tap adpaters that the installer asks you to.

To download the vpn configuration file from our server we'll be using pscp which is putty scp. It is used to copy files to and from webservers to desktop hosts. Go to <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">putty downloads site</a> and download the pscp.exe for your system. 

To run pscp open cmd `cd <your directory with pscp download>` and press enter. This should open the pscp directory. Now type `pscp`
and press enter. For e.g:

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img13.png">

To download the .ovpn config file type the code `pscp root@<your web server's ip address>/root/<profilename>.ovpn <your download
directory>` For e.g for the guest config file, it will look something like this.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img14.png">

Now run <b>open vpn gui</b> and right click on import.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img10.png">

Select the directory where you downloaded the .ovpn profile using pscp and click ok. Now right click on the open vpn icon in the windows tray again, and chose the profile. Click connect

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img11.png">

Its done now! You can see the toast that vpn is connected. Try checking your IP in the browser and your location, it will be changed

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img12.png">

The same .ovpn file can be imported in your phone or other clients on different operating systems. Have fun!

## Thanks for reading and following through, if you wanna have a chat ping me anytime on <a href="t.me/skylanskylion">telegram</a>


  
  
