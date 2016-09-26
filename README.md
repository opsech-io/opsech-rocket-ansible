```
├── ansible.cfg
├── files
│   └── cloudfront_URL_sig.patch
├── group_vars
│   ├── centos_servers
│   └── chat_servers
├── inventory
├── README.md
├── requirements.yml
├── rocket_chat.yml
└── tasks
    ├── cloudfront_patch.yml
    └── get_requirements.yml
```
| file | description |
|------|-------------|
| get_requirements.yml | Install requires role(s) *before* running installation. I tried doing this inline with the install but it checks for all roles to be present first, even if you include |
| rocket_chat.yml | Main kick-off, RocketChat.Server will be installed on hosts provided as `chat_servers` in `inventory` |
| inventory | ini-style file that contains endpoints |

#### Usage:

```
git clone https://github.com/opsech-io/opsech-rocket-ansible.git
cd opsech-rocket-ansible
vi inventory # add some CentOS 7 servers
ansible-galaxy install -r requirements.yml -p roles/ # use this only for the official galaxy role
ansible-playbook -i inventory rocket_chat.yml
```
