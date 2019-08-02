start test machine with static ip and copy ssh-key
cd ./Vagrant && vagrant up
from root dir:
ansible-playbook -i hosts main.yml
