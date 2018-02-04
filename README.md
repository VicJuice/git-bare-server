# git-bare-server

=================

A minimal GIT server.

## volumn directories

```bash

    mkdir ~/git-server-data

    mkdir ~/git-server-data/git-shell-commands

    mkdir ~/git-server-data/.ssh

    touch ~/git-server-data/.ssh/authorized_keys

```

## add ssh pub key to authorized keys

```bash

    cp ~/.ssh/id_rsa.pub ~/git-server-data

    echo `cat ~/.ssh/id_rsa.pub` >> ~/git-server-data/.ssh/authorized_keys

```

## init bare git repo

```bash

    mkdir ~/git-server-data/repo.git

    cd ~/git-server-data/repo.git

    git --bare init

```

## build image

```bash

    docker-compose build

```

## run image

```bash

    docker-compose up -d

```

## Clone the repo from a client

```bash

    git clone ssh://git@localhost:2222/git/repo.git

```

## Notice

If you wanna to only allow git user can access the repo, change all the volumn owner and wrx rights to git. any change can be seen in dockerfile.
