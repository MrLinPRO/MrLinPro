MACHINES = {
  :"kernel-update" => {
              #Указали box виртуалки, который будем использовать
              :box_name => "generic/ubuntu2204",
              #Указали версию
              :box_version => "4.3.12",
              #Указали количество ядер ВМ
              :cpus => 2,
              #Указали количество озу
              :memory => 1024,
            }
}

Vagrant.configure("2") do |config|
  MACHINES.each do |boxname, boxconfig|
    #Отключили проброс шары в ВМ
    config.vm.synced_folder ".", "/vagrant", disabled: true
    #Применили конфиг
    config.vm.define boxname do |box|
      box.vm.box = boxconfig[:box_name]
      box.vm.box_version = boxconfig[:box_version]
      box.vm.host_name = boxname.to_s
      box.vm.provider "virtualbox" do |v|
        v.memory = boxconfig[:memory]
        v.cpus = boxconfig[:cpus]
      end
    end
  end
end
