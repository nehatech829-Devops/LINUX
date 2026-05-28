# **User and Group Management**



User management in Linux involves creating, modifying, and deleting user accounts and groups to maintain a secure and organized multi-user environment. It ensures that each person or system process has a unique identity (User ID/UID) and appropriate access to resources.



#### **Types of Users in Linux**



Linux is a multi-user operating system, meaning multiple users can access and operate the system simultaneously. Each user type serves a specific purpose and has different levels of access and control.



Root (Superuser): Full system control. Can install software, change config files, and delete anything. Powerful but risky.



Regular User: Limited access. Can create files, run applications, but not modify system-level settings.



Sudo User: Regular user with temporary admin rights via the sudo command. Common in modern systems.



System/Service Account: Non-human accounts used by services (e.g., mysql, nginx). Limited privileges.



Guest User : Temporary users with minimal privileges. Changes are not saved after logout. (desktop environment specific).



#### **Commands**



Create User Account:

useradd shub



Check User Account Properties:

grep shub /etc/passwd



Set User Password:

passwd shub



Switch User:

su shub



Delete User:

userdel shub



Change Login Name:

usermod -l devops shub





### **User Groups**

A user group is a collection of users. If you give permission to a group, all users in that group get the same access. This makes it easier to manage file and system permissions for many users at once.



#### **Types of Group** 



Primary Group (Default for files)



Every Linux user is assigned one primary group.

When a user creates a file, the group ownership of that file is automatically set to their primary group.

By default, this group usually has the same name as the user.

It helps manage file ownership cleanly without much extra configuration.





Secondary Group(Additional Permissions)



A user can be a part of multiple secondary groups.

These groups provide extra access to files, folders, or services.

They are commonly used for team-based access or system-level permissions (e.g., accessing Docker, video devices, or running sudo).



#### **Commands**



Add Group:

groupadd ibmgrp



Add User to Group:

gpasswd -a ajay ibmgrp



Remove User from Group:

gpasswd -d virat ibmgrp

