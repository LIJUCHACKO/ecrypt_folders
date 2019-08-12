##### 'ecrypfs_mount_mine' is an easy way to keep selected folders encrypted  using ecryptfs utilities  ####

Installation
------------------------------------
Run install script in this folder
```
chmod 777 install
sudo ./install 
```
Installation script will do following things for you

  1. Copy 'ecrypfs_mount_mine' & 'encrypt_folder' to /usr/bin folders and give executiong permission to the files
  
  2. Add extra line to /etc/sudoers as given below (you can use visudo command)
  ```
      ALL ALL = NOPASSWD: /usr/bin/encrypt_folder
  ```
  3. Setup configuration file for new user
  
Create empty folders and put the absolute path of the folders in .ecryptfs/folder_list (in your home folder), one below the other

Run
```
    ecryptfs_mount_mine -m
```
Enter password given during installation processes and proceed. Folders will be listed one after the other.

After mounting you can use the folder as usual. After unmounting or after restarting PC, the folders will be empty, you have to mount it using above command.

 

Note
-------------------------------------------
  1. Always mount folders before using them.
  
  2. Additional folders can be added in .ecryptfs/folder_list later, but the folder should be empty to start with.
  
  3. Keep a backup of .ecryptfs folder.
  
  4. Your encrypted contents are kept in '<folder name>_ecrptfs' folder, do not delete or rename or relocate them
  
  5. Contents of folder will not be visible if folder is not mounted 
  
  6. Use 'ecryptfs_mount_mine -m ' to mount folders.
    Give 'y' answer to the corresponding folders
    
  7. Use 'ecryptfs_mount_mine -um ' to umount folders.
    Give 'y' answer to the corresponding folders
    
  8. Your password is actually the Wrapping passphrase   
  
  9. If you are getting any mounting error regarding keyring , rerun install script
  
  10. Install script is required to setup encryption for another user on the same PC.

  
Migrating to new system or new user
-----------------------------------------------------
  If you want to open encrypted folder from another user or after OS reinstallation do the following
  
  	1. Copy .ecrypfts folder to new home folder 
	
	2. If you are relocating the folder then  <folder> and <folder>_ecrptfs should be placed side by side
	
	3. .ecryptfs/folder_list should contain the absolute path the folders
	
	4. Run install script 
