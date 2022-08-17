BOX_IMAGE = "fedora36"
NODE_COUNT = 1

Vagrant.configure("2") do |config|
  #config.ssh.private_key_path = "id_rsa"
  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant"
  #config.ssh.pty = true
  config.vm.synced_folder ".", "/vagrant", disabled: true
  (1..NODE_COUNT).each do |i|
    config.vm.define "fedora36#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
      subconfig.vm.hostname = "fedora36#{i}"
      subconfig.vm.provider "hyperv" do |h|
        h.cpus = 2
        h.memory = 2048
        h.maxmemory = 4096
        h.vm_integration_services = {
          guest_service_interface: true,
        }
      end
    end
  end
end