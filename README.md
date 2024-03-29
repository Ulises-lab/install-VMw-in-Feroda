# install-VirtualBox-on-Feroda


## In this section I would like to show you how can you install VirtualBox in your Fedora system trhough CLI...


**Let's start!**
---

First of all. You have to run the commands update and upgrade in your Fedora, so our first task is run that commads:


1.-
   
    sudo dnf update 
    sudo dnf upgrade -y
   

2.- **Install dependencies:**

    sudo dnf install -y @development-tools  
    sudo dnf install -y kernel-headers kernel-devel dkms elfutils-libelf-devel qt5-qtx11extras

3.- **Install more tools**
    
    
    
    install -y @development-tools
    sudo dnf install -y kernel-headers kernel-devel dkms elfutils-libelf-devel qt5-qtx11extras


3.- **Add VirtualBox RPM repository in yum.repos.d**


    
    cat <<EOF | sudo tee /etc/yum.repos.d/virtualbox.repo
     [virtualbox]
     name=Fedora - VirtualBox Repo
     baseurl=http://download.virtualbox.org/virtualbox/rpm/fedora/35/x86_64/
     enabled=1
     gpgcheck=1
     repo_gpgcheck=1
     gpgkey=https://www.virtualbox.org/download/oracle_vbox_2016.asc 
    EOF
     
*In my case I'm using Fedora **35**, so you have to change it in the variable **baseurl** and check what architecture are you using, in my case is x86_64 and also here you are the webpage to check the URL to download the specific VirtualBox RPM to Fedora: https://download.virtualbox.org/virtualbox/rpm/fedora/* 

3.- **Import gpgkey**

    
    sudo dnf search VirutalBox
    
4.- **Install VirtualBox on it**

     
    sudo dnf install VirutalBox-7.0
    






