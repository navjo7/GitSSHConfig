# Connect to git hub using ssh from local machine


### Installation 

1. Go to .ssh folder `cd ~/.ssh`

1. ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

1. `Enter file in which to save the key (/Users/navjotsingh/.ssh/id_rsa):` enter the key name here

1. `Enter passphrase (empty for no passphrase):` leave it empty

1. `Enter same passphrase again:` leave empty 

1. Key will be generated and you will see an image of the key in terminal.

1. To check type `ls -al`, you will see all the keys you have already generated.

1. If you have multiple git accounts and multiple ssh keys for them then type `sudo nano config`

1. start ssh-agent `eval "$(ssh-agent -s)"`

1. add the below code and save the file

```
  Host USERNAME
  HostName github.com
  User git
  IdentityFile ~/.ssh/KEY_NAME

```
1. Add the ssh to key to the ssh agent `ssh-add -K ~/.ssh/KEY_NAME`

1. No add the key to your git hub account
    * Login to github -> Click on profile -> go to Setting -> Left side click on `SSH and GPG keys` 

1. In you machine's terminal `pbcopy < ~/.ssh/KEY_NAME.pub` and enter.

1. No come to git hub and paste inside key, and give any title

1. Change the global email `git config --global user.email "email@example.com"` to confirm `git config --global user.email` (By this user only the commit will be made on the repo)



1. to change the username and email for current project  
```
    git config user.name USERNAME
    git config user.email USERNAME@example.com

```

1. Using one ssh from a single machine out of multiple ssh for different git accounts  `git remote set-url origin https://USER@github.com/USER/REPO.git`

## Authors

* **Navjot** 