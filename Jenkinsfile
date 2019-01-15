---
- hosts: all
  tasks:
  -  name: install httpd
     yum:
       name: httpd
       state: latest
  -  name: Start apache services
     service: name=httpd state=restarted enabled=yes
  -  name: copy index file
     copy: src=/ansible/index.html dest=/var/www/html
     notify:
     - restart apache
  handlers:
  -  name: restart apche
     service: name=httpd state=restarted
