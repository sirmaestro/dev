# dev

# Useful commands
Generate Public/Private keys to ssh into server
```
ssh-keygen
cat ~/.ssh/id_rsa.pub | ssh USER@HOST "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
```

Zip directory with exclusion
```
zip -r node.zip . -x "**/node_modules/*"
```
```
zip -r dir.zip dir/ -x */\.* *.git* \.* *.zip *.csv *.json *.rb *.bak *.swp *.back *.merge *.txt *.sh dir1/node_modules/**\* dir1/bower_components/**\* dir1/dist/**.*
```

Rsync - Move files but better
```
rsync /path/to/source-file /path/to/destination
```
Command | Description
------------ | -------------
`-a` | Recursive transfer, the transfer of file modification times, file permissions, symbolic links
`-v` | Increase verbosity
`-h` | Output numbers in a human-readable format
`-P` | Shows progress and keeps partially transferred files
`-n` | Dryrun
`-z` | Compress file data during the transfer
`--remove-source-files` | Sender removes synchronized files (non-dir)
`--ignore-existing` | Skip existing files
`--delete` | Delete destination files
`--exclude` | Exclude source files e.g. `--exclude 'path'

Check SMB shares on a host
```
smbclient -L host
```

Mount SMB share in linux
```
mount -t cifs -o username=user_name //server_name/share_name /mnt/data
```
e.g.
```
mount -t cifs -o username=plex //192.168.1.222/media /mnt/temp
```
# Tmux
Command | Description
------------ | -------------
`tmux` | Start a new session
`tmux ls` | List all sessions
`Ctrl` `b`, `d` | Detach from session
`tmux attach -t` | Re-attach a detached session 
