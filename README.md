``Репозиторий для создания образа в Vagrant Ubuntu 22.04 и ядром 6.5.0-28``

``box_version была взята с https://app.vagrantup.com/generic/boxes/ubuntu2204``

``Обновление ядра до версии 6.5.0-28 производилось путём выполнения команды:sudo apt install linux-generic-hwe-22.04,`` 

``без подключения репозитория(как в методичке для centos) в следствие отсутсвия ссылки на его загрузку(конкретно для ubutnu 22.04).``

``ДОПОЛНЯЮ ФАЙЛ СПИСКОМ КОМАНД И ИХ ОПИСАНИЕМ:``

  ```uname -r - проверил версию ядра.```
     ```sudo apt install -y https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.deb - попытался подключить репозиторий - .deb, не удалось.```
   ```sudo add-apt-repository ppa:tuxinvader/jammy-mainline -y - нашел иной репозиторий, подключил его.```
     ```sudo apt-get update - выполнил обновление системы```
    ```sudo apt-get install linux-generic-6.0 - попытался обновить ядро из подключенного репо - не удалось из-за версии ядра дистрибутива.```
    ```sudo reboot```
  ```uname -r - проверил повторно версию ядра, осталась неизменной 5...```
    ```sudo apt install linux-generic-hwe-22.04 - нашел команду для hwe, выполнил обновление ядра до версии 6.... - УШЛО огромное количество времени на поиск беспл.VPN```
   ```  sudo reboot```
 ```uname -r - проверка версии, 6...```
 ```exit ```
