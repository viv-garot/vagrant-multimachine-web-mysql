Vagrant.configure("2") do |config|

  (1..2).each do |i|
    config.vm.define vm_name="web0#{i}" do |node|
      node.vm.box = "vivien/nginx64"
      node.vm.hostname = vm_name
      node.vm.network "private_network", ip: "192.168.50.#{10+i}"
      node.vm.network :forwarded_port, guest:80, host: "#{8080+i}"
    end
  end

    config.vm.define "mysql" do |mysql|
      mysql.vm.box = "vivien/mysql"
      mysql.vm.hostname = "mysql"
      mysql.vm.network "private_network", ip: "192.168.50.100"
    end
  end
