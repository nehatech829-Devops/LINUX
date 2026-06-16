## **Linux ACL (Access Control Lists)**



**Overview**



Access Control Lists (ACLs) provide a flexible permission mechanism in Linux. ACLs allow administrators to grant specific permissions to individual users and groups without changing the file's owner or group.



ACLs extend the traditional Linux permission model (Owner, Group, Others).





**Why Use ACL?**



Traditional permissions allow access control for:



\* Owner

\* Group

\* Others



ACLs allow permissions for:



\* Multiple users

\* Multiple groups

\* Fine-grained access control





**Check ACL Support**



Verify that ACL tools are installed:



```bash

getfacl --version

setfacl --version

```



Install ACL package (Ubuntu/Debian):



```bash

sudo apt update

sudo apt install acl

```



\---



**View ACL Permissions**



Use `getfacl` to display ACL entries.



```bash

getfacl file.txt

```



Example Output:



```bash

\# file: file.txt

\# owner: neha

\# group: neha

user::rw-

group::r--

other::r--

```





**Set ACL Permissions**



\### Grant Read Permission to a User



```bash

setfacl -m u:john:r file.txt

```



\### Grant Read and Write Permission



```bash

setfacl -m u:john:rw file.txt

```



\### Grant Permissions to a Group



```bash

setfacl -m g:developers:rwx project.txt

```



\---



\## Verify ACL Entries



```bash

getfacl file.txt

```



Example:



```bash

user:john:rw-

group:developers:rwx

```



\---



\## Remove ACL Permissions



Remove ACL for a specific user:



```bash

setfacl -x u:john file.txt

```



Remove ACL for a group:



```bash

setfacl -x g:developers file.txt

```



Remove all ACL entries:



```bash

setfacl -b file.txt

```



\---



\## Default ACLs



Default ACLs automatically apply permissions to newly created files and directories.



Set default ACL:



```bash

setfacl -d -m u:john:rwx shared\_folder

```



Verify:



```bash

getfacl shared\_folder

```



\---



**Common ACL Commands**



| Command                         | Description          |

| ------------------------------- | -------------------- |

| getfacl file.txt                | View ACL permissions |

| setfacl -m u:user:rw file.txt   | Add ACL for user     |

| setfacl -m g:group:rwx file.txt | Add ACL for group    |

| setfacl -x u:user file.txt      | Remove user ACL      |

| setfacl -b file.txt             | Remove all ACLs      |

| setfacl -d -m u:user:rwx dir    | Set default ACL      |







**Advantages of ACL**



\* Fine-grained permission control

\* Multiple users can have different permissions

\* Better collaboration in shared environments

\* Improves security and flexibility



**Conclusion**



ACLs provide advanced permission management beyond traditional Linux file permissions. They are useful in multi-user environments where different users require different levels of access to files and directories.



