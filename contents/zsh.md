# ZSH
## Install as root

```sh
$ sudo su
$ cd
$ sudo apt install zsh -y
```

## Get bash

```sh
$ sudo sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

## Settings
#### Bash:

```sh
$ sudo vim .zshrc
```

#### [.zshrc]

```sh
export ZSH="/opt/oh-my-zsh/.oh-my-zsh"
ZSH_THEME="essembeh"
```

#### Conf:

```sh
$ sudo mkdir /opt/oh-my-zsh
$ sudo cp -r /home/<user>/.oh-my-zsh/ /opt/oh-my-zsh/
```

## Copy Zsh root to user

```sh
$ sudo cp -r /root/.zshrc /home/<user>
```

## Activate Zsh

```sh
$ chsh -s `which zsh`
```

## Upgrade

```sh
$ upgrade_oh_my_zsh
```

## Add Zsh shell to all the users
#### Zshrc export:

```sh
$ for i in <user1> <user2> <user3> <user4> <userX>; do cp /root/.zshrc /home/${i}; chown ${i} /home/${i}/.zshrc; done
```

#### Active Zsh shell

```sh
$ for i in <user1> <user2> <user3> <user4> <userX>; do chsh --shell=`which zsh` ${i}; done
```

## If [oh-my-zsh] Insecure completion-dependent directories detected

#### Open file in the root directory:

```sh
$ sudo vim /root/.zshrc
```

#### Disable compfix:

```sh
ZSH_COMPFIX_DISABLE=true
```

##### Zshrc export and active zsh shell again: (recommended)

```sh
$ sudo chmod -R 755 /opt/oh-my-zsh
```