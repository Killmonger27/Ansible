Vagrant.configure("2") do |config|
  (1..2).each do |i|
    config.vm.define "webserver#{i}" do |web|
      web.vm.network "forwarded_port", guest: 80, host: 8080 + i
      web.vm.box = "ubuntu/jammy64"
      web.vm.network "private_network", ip: "192.168.56.1#{i}"
      web.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 1
      end
    end
  end
end