Vagrant.configure("2") do |config|

  (1..2).each do |i|
    config.vm.define vm_name="web0#{i}" do |node|
      node.vm.box = "vivien/nginx64"
      node.vm.hostname = vm_name
      node.vm.network "private_network", ip: "192.168.50.1#{i}"
      node.vm.network :forwarded_port, guest:80, host: "808#{i}"
    end
  end
end
