# privatevpn
This is a self hested vpn on a untuntu web server. Most normal Vpn providers ask for a premium for their services and you wont have no way of knowing that they wont sell your info to third parties. A self hosted vpn is cheaper and gives you the control of your datda. I've illustated the steps below on how to create your own private vpn and host it for free for the first 10 months.

# getting  a server
The first is getting a  web server to host your vpn, i've used the digital ocean starter ubuntu server which comes ad 5$/month, but you can sign up with your <a href="https://education.github.com/packgithub">student account</a> and get 50$ digital ocean credit and host it for free.
You can also use aws google webservices or any of other free cloud services to host it for free.

## For digital ocean

1. Go to create a droplet
<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img1.png">

  Select the lowest tier for 5$/month. Our vpn server doesnt require much resources so this should be more than enough to run it.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img2.png">

  Now you'll get a mail in your digital ocean registered email id with the login initials for your ubuntu server.

  It will look something like this.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img3.png">

  Now your web server is read for you to tinker with.
  Go to your digital ocean dashboard and copy the IP address.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img4.png">

2. Accessing your ubuntu webserver

  Now to open the webserver, we're using putty for windows. Use can use ssh on a terminal if you have a mac or gnu/linux. Go to putty     website and <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">download putty</a>
  
  Now run the installer and open putty. You'll be greeted with the login screen. Put in the IP address of the server and click open.

<img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img5.png">

  For the first time you can enter the username as <b>root</b> and the password that you get in your mail. You dont need to copy it all. 
  YOu can click mouse button to paste the password in the putty terminal. You'll be asked to change your default password. Enter your
  password again and create a new password.
  
  Now you're ready to go. Its good convention to update your system the first time so run the following commands:
  
  `sudo apt update -y` press enter and type your password.
  
  `sudo apt upgrade -y` and repeat
  
  Now I recommend you type `reboot` and restart your ubuntu webserver. The putty client will show connection stopped. Wait a few seconds
  and open putty again. Login in to your webserver.
  
  <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img6.png">
  <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img7.png">
  
3. Setting up the vpn

  Type the following commands:
  
  `wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh`
  
  <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img8.png">
  
  Run the script and follow the instructions. When it asks for a client name, you can put in anything like, desktop or phone. This 
  client allows you to make 250 different clients.
  
   <img src="https://github.com/skylanskylion/privatevpn/blob/master/Private%20vpn/Images/img9.png">
   
  Now type the following command:
  
  `chmod 777 openvpn-install.sh`
  
  To to create more profiles you can type `./openvpn-install.sh` and remove or add more profiles. You can also change the configuration
  if you want to but it is not recommended.
  
## Setting up the VPN clients

We will be using open vpn to access our vpn server. Download the latest open vpn client from the
<a href="https://openvpn.net/community-downloads/"community> downloads page</a> or you can use
the version that i've provided.
  
  
