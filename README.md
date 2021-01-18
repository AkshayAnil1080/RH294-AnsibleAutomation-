#1. Is Ansible used for automation? since decades before the development of Ansible, automation is been used.
Why Ansible now?

Earlier, automation was achieved by the scripting language by using the imperative approach, whcih means the script should include two things
1. what do you want to do?
2. How do you want to do.?

On the other hand, Ansible behaves intelligently. It has the declarative approach. The programmer has to tell jsut one thing.
1. What do you want to do?

Ansible automatically figures out how to do.



#2. POINTS

- [x] __Why Ansible?__

- [x] __Ansible automation has two ways:__

- [x] __USE CASE OF ANSIBLE IN AMAZON:__

- [x] __How AWS is using the ansible?__

- [x] __Ansible clarity and the power of AWS]__

- [x] __MANAGING CLOUD WITH ANSIBLE.__

- [x] __Cloud control with dynamic Inventory:__

- [x] __Migration made easy__

- [x] __Securely and Safely Automation with no latency.__


# Ansible PlayBook that does the following operations in the managed nodes:

- [x] __ Configure Docker__
- [x] __ Start and enable Docker services__
- [x] __ Pull the httpd server image from the Docker Hub__
- [x] __ Run the docker container and expose it to the public__
- [x] __ Copy the html code in /var/www/html directory and start the web server__






# HTTPD SERVICE AS IDEMPOTENT


PROBLEM STATEMENT:
The httpd service is not idempotent in nature, ie it always restarts the service if some changes been made in conf file or not.




INTITUTION:
With the use of notify and handler module, we made the httpd service restarts only when there is some change in conf file only.



![](outputs/1.jpg)






# Configure Hadoop and start cluster services using Ansible Playbook


![](outputs/task.jpeg)

![](outputs/playbook_output.jpg)

![](outputs/cli_namenode_output.jpg)

![](outputs/aws_output.jpg)



# Summary:
# day 1 (03-11-2020)

👉 What is Ansible & why it is used ?

 ✔1. It is a software provides automation and has its own personal language to write a code and follows a declarative approach, where user has to enter the input of “what to do”, it automatically figures out how to do.

👉 What is Automation & where it is used ?

 ✔2. Automation is to make a program do the work. It is mainly used for performing the same task again and again.

👉 What is difference between Imperative & Declarative Language?

 ✔3. Imperative approach needs how and what to do as input, whereas declarative approach only needs what to do as input.

👉 How can we use imperative & declarative language ?

 ✔4. Imperative language us been used since decades using various software, and declarative is presently used with the Ansible software.

👉 What is Configuration Management ?

 ✔5. It is used to configure some task, and it has two ways: Manual and Automation.

👉 How to install ansible?
 
 ✔6. ”pip3 install ansible"

👉 What is inventory?

 ✔7. a file in the controller node that contains all the target IP, protocol, user and password.

👉 How to start httpd service using ansible command ?

 ✔8. ansible <target IP> -m service -a "name=httpd state=started"

# day2 4-11-20

👉 Explain ansible architecture.

 ✔6. it comprises of control node and target node. - is a system where we install ansible & write a code and n no. of target node .It is a system where we do operations. We control all the target nodes with the help of the controller node.

👉 What is controller node and target node?

 ✔7. Controller node is a system where we install ansible & write a code and n no. of target node. It is a system where we do operations. We control all the target nodes with the help of the controller node.

👉 How to install ansible?

 ✔8. ”pip3 install ansible"

👉 What is inventory?
 
 ✔9. a file in the controller node that contains all the target IP, protocol, user and password.

👉 How to start httpd service using ansible command ?

 ✔10. ansible <target IP> -m service -a "name=httpd state=started"

# day3 5-11-20

👉 What is Configuration Management ?

 ✔11. It is used to configure some task, and it has two ways: Manual and Automation.

👉 Explain ansible architecture.

 ✔12. it comprises of control node and target node. - is a system where we install ansible & write a code and n no. of target node .It is a system where we do operations. We control all the target nodes with the help of the controller node.

👉 What is controller node and target node?

 ✔13. Controller node is a system where we install ansible & write a code and n no. of target node. It is a system where we do operations. We control all the target nodes with the help of the controller node.


# day4 24 November 2020

👉 What provide intelligence to ansible?

 ✔14. The concept of playbook and making the list of plays make the ansible a very intelligent software.

👉 Which format is used to write plays in Ansible Playbook?

 ✔15. JSON / YML format: to use key pair value as ansible is a declarative lang, if you want to declare (eg x=5), key value pair is req.

👉 How to increase the readability of the code?
✔16. By modifying the code by using the keywords like “hosts” , “tasks” to make it easy and redable.

👉 What does YAML signify?

 ✔17. YAML: Ansible used YAML programming language to write a playbook

👉 Which command is used to check the syntax of Ansible Playbook ?

 ✔18. ansible-playbook --syntax-check filename.yml

👉 What are the two approach used for Configuration management using Ansible?
 
 ✔19. a. Manual way using adhoc 
         b. Automated way by using playbook
👉 What are Ad-hoc commands?

 ✔20.  adhoc: it is the manual way of using ansible by typing command for every step.


# day5 25 November 2020

👉 What are the pre-requisites for installing packages in Managed Nodes?

 ✔21. Creating directory, mounting and configuring yum.

👉 What is the ansible module name for creating dir?

 ✔22. File and it has arguments state and path.

👉 How does ansible explore about all the required information of Managed Node?

 ✔23. After running the command, GATHERING FACTS occurs to explore the information about the managed node.

👉 What is the use of -v option in ansible playbook command and how to increase the verbosity?

 ✔24. -v stands for verbosity , it actually defines the whole process in more brief and can be used to max as 5 times i.e -vvvvv.

👉 How to configure yum, create directory, mount, install packages and enable firewalld service using ansible?

 ✔25. -hosts: all

//create directory
 -file:
   state: directory
   path: "dvd1"

//mount
 -mount:
   src: “/dev/cdrom"
   path: "/dvd1"
   state: mounted
   fstype: "iso9660"

//configure yum
 -yum_repository:
   baseurl: "/dvd1/AppStream"
   name: "dvd1"
   description: "dvd1 for package"
   gpgcheck: no

 -yum_repositorty:
   baseurl: "dvd1/BaseOS"
   name: "dvd2"
   description: "dvd2 for package"
   gpgcheck: no
 
//conf. web server
 -package:
   name: httpd
   state: present

 -copy:
   dest: "/var/www/html/filename.html"
   content: "this is my website"

 -service:
   name: "httpd"
   state: started
   enabled: yes

 -firewalld:
   port: 80/udp
   state: enabled
   permanent: yes
   immediate: yes


👉 What is the use of firewall-cmd --list-port?

 ✔26. To show the port allowed by the firewall

👉What is the difference between ‘ ‘ and “ “ in YAML ?

 ✔27. Escape sequences are used under “  “ .
 whereas in ‘ ‘  it is passed as literals(copy as it is)


