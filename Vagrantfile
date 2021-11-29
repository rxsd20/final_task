# -*- mode: ruby -*-
# vi: set ft=ruby :
linux_nodes = {
#    "bastion" => { :ip => "192.168.150.10", :cpus => "1", :mem => "1024"},
    "wordpress" => { :ip => "192.168.150.20", :cpus => "2", :mem => "2048"},
#    "monitoring" => { :ip => "192.168.150.40", :cpus => "2", :mem => "2048"},
#    "backup" => { :ip => "192.168.150.50", :cpus => "4", :mem => "2048"}
}
 
Vagrant.configure("2") do |config|
  config.vm.box = "generic/centos8"
    linux_nodes.each_with_index do |(hostname, cfg), index|
    config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "/home/vagrant/.ssh/id_rsa.pub"
    config.vm.define hostname do |node|
      node.vm.provider :libvirt do |libvirt|
        libvirt.cpus = cfg[:cpus]
        libvirt.memory = cfg[:mem]
        libvirt.nic_model_type = "virtio"
      end
      node.vm.hostname = hostname
      node.vm.network :private_network,
        :ip => cfg[:ip],
        :libvirt__forward_mode => "nat",
        :libvirt__dhcp_enabled => false,
        :libvirt__network_name => "proekt",
        :libvirt__host_ip => "192.168.150.1",
        :libvirt__netmask => "255.255.255.0"
     end
    end
   config.vm.synced_folder "./", "/vagrant", disabled: false
   config.vm.provider :libvirt do |libvirt|
     libvirt.graphics_type = "spice"
     libvirt.video_type = "qxl"
     libvirt.video_vram = "16536"
     libvirt.input :type => "tablet", :bus => "usb"
   end
   config.vm.provision "shell", inline: <<-SHELL
     sudo echo PasswordAuthentication yes >> sudo /etc/ssh/sshd_config
     cat /home/vagrant/.ssh/id_rsa.pub >> /home/vagrant/.ssh/authorized_keys
   SHELL
   config.vm.provision "ansible" do |ansible|
     ansible.playbook = "main.yml"
end
end
