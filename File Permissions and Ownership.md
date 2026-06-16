## **File Permissions and Ownership**



**Overview**



Linux provides powerful commands to manage file permissions and ownership. The `chmod` command is used to change file permissions, while the `chown` command is used to change file ownership.







#### **chmod Command**



What is chmod?



The `chmod` (Change Mode) command is used to modify the permissions of files and directories.



Permission Types



| Symbol | Permission | Value |

| ------ | ---------- | ----- |

| r      | Read       | 4     |

| w      | Write      | 2     |

| x      | Execute    | 1     |







Viewing Permissions



```bash

ls -l

```



Example Output:



```bash

\-rw-r--r-- 1 neha neha 1024 Jun 16 file.txt

```



Explanation:



\* Owner: rw- (Read + Write)

\* Group: r-- (Read)

\* Others: r-- (Read)







#### **Using chmod with Numeric Method**



Give Full Permission to Owner



```bash

chmod 700 file.txt

```



Give Read and Execute Permission



```bash

chmod 755 script.sh

```



Make a Script Executable



```bash

chmod +x script.sh

```



Remove Write Permission



```bash

chmod -w file.txt

```



Add Execute Permission



```bash

chmod u+x script.sh

```







**Common chmod Examples**



```bash

chmod 644 file.txt

chmod 755 directory

chmod 777 shared\_folder

chmod +x backup.sh

```







#### **chown Command**



What is chown?



The `chown` (Change Ownership) command changes the owner and group of a file or directory.







Syntax



```bash

chown owner file

```



Example:



```bash

sudo chown neha file.txt

```



\---



\## Change Owner and Group



```bash

sudo chown neha:developers file.txt

```



\---



\## Change Ownership Recursively



```bash

sudo chown -R neha:developers project/

```



The `-R` option applies changes to all files and subdirectories.



\---



\## Verify Ownership



```bash

ls -l

```



Example Output:



```bash

\-rw-r--r-- 1 neha developers 1024 Jun 16 file.txt

```



\---



##### **Difference Between chmod and chown**



| Command | Purpose                      |

| ------- | ---------------------------- |

| chmod   | Changes file permissions     |

| chown   | Changes file owner and group |



Example:



```bash

chmod 755 script.sh

sudo chown neha:developers script.sh

```



\---



###### **Best Practices**



\* Follow the principle of least privilege.

\* Avoid using `777` permissions unless absolutely necessary.

\* Use `chmod +x` for executable scripts.

\* Verify ownership after using `chown`.

\* Use recursive options carefully.







Conclusion



The `chmod` and `chown` commands are essential Linux administration tools. Understanding permissions and ownership helps improve system security, user management, and file access control.



