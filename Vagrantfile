Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
# config.trigger.after :up do |trigger|
#   run "subscription-manager register --username <username> --password <password> --auto-attach
#   trigger.name = "After-Up Trigger ..."
#   trigger.info = "Trigger Execution ..."
#   trigger.run = { path:"subscription-manager register --username <username> --password <password> --auto-attach"}
# end

  config.vm.define :citus do |citus|
#   citus.vm.box = "bento/centos-6.10"
#   citus.vm.box = "clouddood/RH7.5_baserepo"
    citus.vm.box = "clouddood/RH7.9_infra"
    citus.vm.host_name = "citus.test.dev"

    citus.ssh.forward_agent = true

    citus.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_citus_server.yml"
#     ansible.playbook = "deploy_BaseSystem.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   citus.vm.network :private_network, ip: "10.0.1.56"
    citus.vm.network :private_network, ip: "192.168.60.56"
  end
end
