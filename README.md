# Setup_Raspberry_without_mouse-_and_keyboard

## Step 1 - flash SD card with latest Raspbery OS
  	
	Download latest Raspberry OS light image (ex. Debian Buster):-os/
	>> insert the SD card into your card reader
	>> unzip file and flash SD card using a tool like 'balenaEtcher'
		https://www.balena.io/etcher/


## Step 2 - enable ssh

	>> take out the SD card and insert again
	>> create empty file 'ssh' in the root directory
	#cd /.../boot/
	#touch ssh
	>> eject the SD card


## Step 3 - change default password for user 'pi'
	
	>> insert the SD card into the Raspberry Pi and power it up
	>> ssh to the Raspberry and login with user 'pi' and password 'raspberry'
	#ssh pi@<ip of Raspberry>
	#passwd 
   	>>meraki123
	#sudo reboot

## Step 4 - update Raspberry

	>> ssh to the Raspberry and login with user 'pi' and password 'meraki123'
	#sudo apt-get update
	#sudo apt-get dist-upgrade


## Step 5 - change password for user 'root'
	
	#sudo su
	#passwd root
	#meraki123#
	#exit
	
	
## Step 6 - install tools
	
	#sudo apt-get install vim
	
	
## Step 7 - enable ssh for root 
	
	>> ssh to the Raspberry and login with user 'pi' and password 'meraki123'
	#sudo vim /etc/ssh/sshd_config

	>> change ' #PermitRootLogin prohibit-password'
     	   to          ' PermitRootLogin yes'

	>> restart ssh service
		#sudo /etc/init.d/ssh restart



Have Fun !
