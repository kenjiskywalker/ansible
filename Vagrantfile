#
# カレントディレクトリのVagrantfileを利用する場合
# 「VAGRANT_CWD」をカレントディレクトリで指定する必要があります
#
# VAGRANT_CWD=`pwd`
# echo ${VAGRANT_CWD}

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos65"
  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"
  config.vm.define :"dev" do |dev|
    dev.vm.network :private_network, ip: '192.168.77.11'
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./ansible/dev.yml"
  end
end
