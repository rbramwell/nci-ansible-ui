# nci ansible ui

Simple ansible playbook runner.

It pulls your repository with playbooks and inventories according to project
config (it defines repository path, playbook and inventory directories inside
repository, etc) and allows you to run playbooks with invetories via single
page web interface (with live updates and pretty terminal output).


## Features

* single page web application which immediately responds on any
user interaction. This app doesn't use http api, it's built using socket.io
* online console output which is very close to terminal emulator
* can run one playbook with different inventories (sequentially)
* working with any mercurial, git repositories (no matter is it service like
github, bitbucket or private server, all you need is authenticate user from
which nci server is running without password e.g. by ssh key)
* minimal dependencies (only nodejs, scm client and ansible are required)


## Quick setting up

Clone quick setup repo, go into it and install dependencies:

```sh

git clone https://github.com/node-ci/nci-ansible-ui-quick-setup && \
cd nci-ansible-ui-quick-setup && \
npm install

```

run server:


```sh

node_modules/.bin/nci

```

that's all, now you can experiment with it by adding/changing projects,
use web interface (on http://127.0.0.1:3000 by default) for run playbooks.

Sample project works with
[repository](https://github.com/node-ci/nci-ansible-ui-sample-playbook)
which contains sample playbooks (some ping, ps ax and other read commands) and
inventory. Inventory defines localhost as target host with following
settings:

```yaml
ansible_host: 127.0.0.1
ansible_user: ansible
```

you should provide such access in order to run sample project.


## License

MIT
