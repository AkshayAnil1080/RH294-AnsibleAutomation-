# Is Ansible used for automation? since decades before the development of Ansible, automation is been used.
Why Ansible now?

Earlier, automation was achieved by the scripting language by using the imperative approach, whcih means the script should include two things
1. what do you want to do?
2. How do you want to do.?

On the other hand, Ansible behaves intelligently. It has the declarative approach. The programmer has to tell jsut one thing.
1. What do you want to do?

Ansible automatically figures out how to do.






# HTTPD SERVICE AS IDEMPOTENT


PROBLEM STATEMENT:
The httpd service is not idempotent in nature, ie it always restarts the service if some changes been made in conf file or not.




INTITUTION:
With the use of notify and handler module, we made the httpd service restarts only when there is some change in conf file only.



![](outputs/1.jpg)
