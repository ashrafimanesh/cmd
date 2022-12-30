# SSH
SSH useful commands:

### Login to server without password
ssh-copy-id [-i [identity_file]] [user@]machine

``` ssh-copy-id -i ~/.ssh/id_rsa.pub user@machine ```

### generate ssh key

``` ssh-keygen -t rsa ```

### SSH examples

1. you will be able to have your ssh command listen on a control socket and wait for commands from subsequent ssh calls.
```
ssh -D localhost:1010 -S /tmp/.ssh1010 -M -fN localhost1010
# (...)
# You can terminate ssh connection
ssh -S /tmp/.ssh1010 -O exit localhost1010

```
### proxychains
1- Check ip
 ````
 proxychains curl ifconfig.me/ip
 ````

### tmux

1- start new session with name
```
tmux new -s test
```

2- Attach to tmux existing session
```
# Sessions list
tmux ls
# To connect to a session
tmux a -t test
```
