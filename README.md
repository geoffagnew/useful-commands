# Linux commands and basics

### Directory basics
`etc/` contains system wide configuration files.

`var/` contains changeable or variable system information. For example, system logs and logs for other software.

`mnt/` or `media/` is where external drives are mounted.

### File manipulation

Moving files from one location to another. For example, if you wanted to move *file1* to the *test* directory
```
mv file1 test
```

Renaming files or directories. For example, if you wanted to rename *file1* to the *file2*
```
mv file1 file2
```

*Note: The Linux system will not prevent you from certain destructive actions. If you are renaming a file and choose a name that already exists, the previous file will be overwritten by the file you are moving. There is no way to recover the previous file if you accidentally overwrite it.*

To delete a regular file
```
rm file4
```

To delete an entire *empty* directory
```
rmdir testing
```

To delete a directory that contains files or other assets
```
rm -r testing
```

To delete all files and sub directories within a directory: 
```
sudo rm -r public_html/*
```

Unzip a compressed file
```
sudo unzip file_name.zip
```

Moving all files from child directory to parent directory. For example, the directory structure looks like this: /public_html/myfiles/. Say you want to move all files (including dot files like .htaccess) from myfiles up one level to public_html. While in public_html, run the following:
```
sudo mv myfiles/* myfiles/.* .
```

### Permissions
Change permissions of web files to the www-data group
```
sudo chown -R yourname:www-data nameofdirectory
```

### SFTP

Pushing file from local to remote. 
```
put localFile
```

Pushing entire local directory to remote. 
```
put -r localDirectory
```

Get file from remote.
```
get remoteFile
```

### Restart Apache
```
sudo service apache2 restart
```

### Restart Nginx
```
sudo service nginx restart
```

### Connecting to VPS

SSH
```
ssh username@yourIpAddress
```

SFTP
```
sftp username@yourIpAddress
```
