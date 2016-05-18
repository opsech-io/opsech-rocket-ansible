```
.
├── ansible.cfg
├── inventory
├── roles
│   └── requirements.yml
└── tasks
    ├── get_requirements.yml
    └── rocket_chat.yml
```
| file | description |
|------|-------------|
| get_requirements.yml | Install requires role(s) *before* running installation. I tried doing this inline with the install but it checks for all roles to be present first, even if you include |
| rocket_chat.yml | Main kick-off, RocketChat.Server will be installed on hosts provided as `chat_servers` in `inventory` |

#### Usage: 

```
git clone https://github.com/opsech-io/opsech-rocket-ansible.git
cd opsech-rocket-ansible
vi inventory # add some CentOS 7 servers
ansible-playbook -i inventory tasks/get_requirements.yml
ansible-playbook -i inventory tasks/rocket_chat.yml
```
