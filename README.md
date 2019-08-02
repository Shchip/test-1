cd ./Vagrant
vagrat up # start test machine with static ip and copy ssh-key
from root dir:
ansible-playbook -i hosts main.yml
