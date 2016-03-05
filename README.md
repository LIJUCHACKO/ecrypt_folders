##### 'ecrypfs_mount_mine' is an easy way to keep selected folders encrypted  using ecryptfs utilities  ####

Installation
------------------------------------
run install from this folder
  sudo ./install 
Installation script will do following things for you
  1.Copy 'ecrypfs_mount_mine' & 'encrypt_folder' to /usr/bin folders and give executiong permission to the files
  2.Add extra line to /etc/sudoers as given below (you can use visudo command)
    ALL ALL = NOPASSWD: /usr/bin/encrypt_folder
  3.Setup configuration file for new user
  

Usage
-------------------------------------------
  1.Use 'ecryptfs_mount_mine -m ' to mount folders
    Give 'y' answer to the corresponding folders.
  2.Create empty folders and put the absolute path of the folders in .ecryptfs/folder_list , one below the other
  3.Keep a backup of .ecryptfs folder.
  4.Your encrypted contents will be kept in '<folder name>_ecrptfs' folder, do not delete or rename or relocate them
  5.Contents of folder will not be visible if folders are not mounted 
  6.Note -Wrapping passphrase is your password  
  7.If you are getting any mounting error due to keyring rerun install script

  
Migrating folder to new system or new user
-----------------------------------------------------
  If you want to open encrypted folder from another user or after OS reinstallation do the following
	copy .ecrypfts folder to new home folder 
	If you are relocating the folder then  <folder> and <folder>_ecrptfs should be placed side by side
	.ecryptfs/folder_list should contain the absolute path the folders
	run install script 
