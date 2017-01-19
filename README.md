# ansible provisioner
  This is an ansible provisioning script installs and runs a Flaskapp in a VagrantVM.

  Steps to follow to uses this provisioner :

  1. Create a new directory test and move into it.
  2. Execute $vagrant init ubuntu/trusty64
  3. This repository is having a Vagrantfile replace the default Vagrantfile with this file.
  4. Now clone the repository under test, Vagrantfile and Provisioning directory should be under test directory.
  5. Execute $vagrant up
  6. In the browser hit http://192.168.33.15:80
