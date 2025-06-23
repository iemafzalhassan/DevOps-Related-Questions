Package Lifecycle Stages: Download → Install → Configure → Upgrade → Remove.

Download- 
we download pacakeage with sudo apt download nginx from a configuration software repository 

install:-
The package manager installs the software onto the system, placing files in appropriate directories and resolving dependencies.

we will install packate by sudo apt install nginx

configure:-
all configuration get set in /etc file such in for nginx file config will be set to /etc/nginx/nginx.conf

upgrade:-
upgrade is to replace the package with newer version
dependencies are re-evaluated and updated 
example:- sudo apt upgrade nginx

remove:- 

pakage get unintsalled from the system 
sudo apt remove nginx

and purge commands is performed to deleet remain configuration files completely


sudo apt purge nginx



