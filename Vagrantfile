ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'
Vagrant.configure(2) do |config|
        # Specifying the box we wish to use
        config.vm.box = "bento/ubuntu-18.04"
        # Adding Bridged Network Adapter
        config.vm.network "public_network"
        if Vagrant.has_plugin?("vagrant-proxyconf")
            config.proxy.http     = "proxy-details"
            config.proxy.https    = "proxy-details"
            config.proxy.no_proxy = "localhost,127.0.0.1"
        end
        # Iterating the loop for three times
        (1..2).each do |i|
                # Defining VM properties
                config.vm.define "vm#{i}" do |node|
                        # Specifying the provider as VirtualBox and naming the VM's
                        config.vm.provider "virtualbox" do |node|
                                node.name = "vm#{i}"
                                node.customize ["modifyvm", :id, "--memory", 4096]
                        end
                end
        end
end
