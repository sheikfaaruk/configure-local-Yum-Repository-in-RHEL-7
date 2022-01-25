# configure-local-Yum-Repository-in-RHEL-7
Follow the Steps to configure local Yum Repository in RHEL 7

# 1. Login as root user in the server & mount RHEL 7 DVD ISO image to any directory e.g. /mnt
 ```sh
mount /dev/sr0 /mnt
 ```
# 2. If you want to mount it permanently, make an entry in fstab file for the same.
 ```sh
vim /etc/fstab
 ```
# 3. Now go to /etc/yum.repos.d/ directory and create a file with any name but extension as .repo 
(e.g. local.repo).
 ```sh
 vim /etc/yum.repos.d./local.repo
 ```
# 4. Now write below mentioned lines in the above file and save it.
 ```sh
[localrepo]
name=localrepo
gpgcheck=0
enabled=1
baseurl=file:///mnt/
 ```
# 5. Now clean yum cache 
 ```sh
yum clean all
 ```
# 6. Now check if your newly created local repository is working or not. Run below command and see the output whether if shows packages or not.
 ```sh
yum repolist
 ```
# 7. Now you can install packages, (e.g install xclock package)
 ```sh
 yum install -y xclock
 ```
