# ansible provisioner
  This is an ansible provisioning script installs and runs a Flaskapp in a VagrantVM.

  Steps to uses this provisioner :

  1. Create a new directory test.
  2. Execute the command under test $vagrant init ubuntu/trusty64
  3. Replace the default Vagrantfile with the file from repository or add the below lines to the Vagrantfile.
     
     config.vm.network "forwarded_port", guest: 80, host: 5000

     config.vm.network "private_network", ip: "192.168.33.15"

     config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    end
    
    config.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end
 
  4. Now clone the repository under test, Vagrantfile and Provisioning directory should be in the test directory.
  5. Execute $vagrant up
  6. App will be running and reachable on http://192.168.33.15:80

  Generated random text messages from the Text url are stored in redis.
  To see the messages

  1. vagrant ssh
  2. Execute $redis-cli -p 1234
  3. now at redis prompt which is running on port execute $keys *
  4. To see the message in each key execute $GET key
