# Useful terminal commands:


### Login to server without password
ssh-copy-id [-i [identity_file]] [user@]machine

``` ssh-copy-id -i ~/.ssh/id_rsa.pub user@machine ```

### Generate ssh key

``` ssh-keygen -t rsa ```

### SSH examples

1. you will be able to have your ssh command listen on a control socket and wait for commands from subsequent ssh calls.
```
ssh -D localhost:1010 -S /tmp/.ssh1010 -M -fN localhost1010
# (...)
# You can terminate ssh connection
ssh -S /tmp/.ssh1010 -O exit localhost1010

```
### Proxychains
1- Check ip
 ````
 proxychains curl ifconfig.me/ip
 ````

### Tmux

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

### Disk space
- Top 10 large directories in `/var/` path.
```
sudo du -a /var/ | sort -n -r | head -n 10
```

- To see journal usage
```
journalctl --disk-usage
```
- To delete old x days journal logs
```
sudo journalctl --vacuum-time=2days
```

### Process
- to kill process by name
```
ps -ef |grep FullNode.jar |grep -v grep |awk '{print $2}'
```
### Docker
- To delete a container logs
```
sudo sh -c 'echo "" > $(docker inspect --format="{{.LogPath}}" CONTAINER_NAME)'
```

## Network

### iptables forward port to other ip
```
echo 1 > /proc/sys/net/ipv4/ip_forward

iptables -F
iptables -t nat -F
iptables -X

iptables -t nat -A PREROUTING -p tcp --dport 80 -j DNAT --to-destination 192.168.12.77:80
iptables -t nat -A POSTROUTING -p tcp -d 192.168.12.77 --dport 80 -j SNAT --to-source 192.168.12.87
```


### Check server network gateway
``` ip r | grep ^def ```
