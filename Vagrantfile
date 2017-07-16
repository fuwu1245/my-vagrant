# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.provision "shell", inline: "sudo apache2ctl restart",run: "always"
    config.vm.box = "debian/jessie64"
    config.vm.network "private_network", ip: "192.168.34.10"
    config.vm.hostname = "vmdebian"

    # Optional NFS. Make sure to remove other synced_folder line too
    #config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }
    # config.vm.synced_folder "../vagrant/scotch-box/sites", "/var/www/html", :mount_options => ["dmode=755", "fmode=644"]
    # config.vm.synced_folder "../vagrant/scotch-box/conf", "/etc/apache2/sites-enabled", :mount_options => ["dmode=755", "fmode=644"]
    # config.vm.synced_folder "../vagrant/scotch-box/sites", "/var/www/html", :nfs => true, owner: "www-data", group: "www-data"
    # config.vm.synced_folder "../vagrant/scotch-box/conf", "/etc/apache2/sites-enabled", :nfs => true, owner: "www-data", group: "www-data"
    config.vm.synced_folder "./sites", "/var/www/html", owner: "www-data", group: "www-data", :mount_options => ["dmode=755", "fmode=644"]
    config.vm.synced_folder "./conf", "/etc/apache2/sites-enabled", owner: "www-data", group: "www-data", :mount_options => ["dmode=755", "fmode=644"]
    #config.vm.synced_folder "./sites", "/var/www/html", type: "rsync"
    #config.vm.synced_folder "./conf", "/etc/apache2/sites-enabled", type: "rsync"
end
