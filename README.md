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

get_requirements.yml - install requires role(s) *before* running installation
    * I tried doing this inline with the install but it checks for all roles to be present first, even if you include

rocket_chat.yml - main kick-off, RocketChat.Server will be installed on hosts provided as `chat_servers` in `inventory`

