Второй системой на рабочий комп на отдельный SSD установлена Ubuntu 22.04-desktop
Настроено VPN-соединение, конфигурация взята из Planet VPN.
По методичке установлены VirtualBox, vagrant, ansible, и др.
В Домашней папке пользователя создана папка VMs
vagrant init - получен файл Vagrantfile
В VagrantFile скачиваются образа ubuntu/focal64 v20240306.0.0 и generic/centos8s v4.3.4 и разворачиваются в виртуалки testvmubuntu и testvmcentos8s в боксах ubuntu и centos соответственно, настройки в соответствии с методичкой.
Проверка 127.0.0.1:8080 ubuntu проведена, приветственная страница Apache2
Проверка ядра centos:

den@Otus:~/VMs$ vagrant ssh centos
[vagrant@testvmcentos8s ~]$ uname -r
4.18.0-516.el8.x86_64

Installed:
  elrepo-release-8.3-1.el8.elrepo.noarch   
  
  sudo yum --enablerepo elrepo-kernel install kernel-ml -y

Installed:
  kernel-ml-6.8.1-1.el8.elrepo.x86_64                                           
  kernel-ml-core-6.8.1-1.el8.elrepo.x86_64                                      
  kernel-ml-modules-6.8.1-1.el8.elrepo.x86_64 
  
[vagrant@testvmcentos8s ~]$ sudo reboot
Connection to 127.0.0.1 closed by remote host.
den@Otus:~/VMs$ vagrant ssh centos
Last login: Tue Mar 26 10:17:22 2024 from 10.0.2.2
[vagrant@testvmcentos8s ~]$ uname -r
6.8.1-1.el8.elrepo.x86_64

  
# l2-vagrant
