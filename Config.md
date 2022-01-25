# 1. Login as root user in the server & mount RHEL 7 DVD ISO image to any directory e.g. /mnt

mount /dev/sr0 /mnt

#2. If you want to mount it permanently, make an entry in fstab file for the same.

# vim /etc/fstab

#3. Now go to /etc/yum.repos.d/ directory and create a file with any name but extension as .repo 
(e.g. local.repo).

# vim /etc/yum.repos.d./local.repo

#4. Now write below mentioned lines in the above file and save it.

[localrepo]
name=localrepo
gpgcheck=0
enabled=1
baseurl=file:///mnt/

5. Now clean yum cache 
# yum clean all

6. Now check if your newly created local repository is working or not. Run below command and see the output whether if shows packages or not.

# yum repolist

7. Now you can install packages, (e.g install xclock package)
# yum install -y xclock
