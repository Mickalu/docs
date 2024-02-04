# connect by ssh connection

```
ssh -i private_key_path root@<ip adresse>
```

# SCP 

```
sudo scp . root@<IP adresse>:< Directory path >
```

# Rsync

Sync local folder to server folder. Change only not same files
```
rsync -az -e "ssh -i <ssh key path>" <Directory want to copy>/* root@<Ip adresse>:< Directory path > 
```

-a : compress files for journey but need more CPU 
-z :
-e : precise how to make the connection. Here by ssh and ssh key. After -e its the command for find ssh key.
