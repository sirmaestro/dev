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

Rsync - Move files with progress
```
rsync --progress /path/to/source-file /path/to/destination
```
`--ignore-existing` - Skip existing files
`--delete` - Delete source files


# Tmux
Command | Description
------------ | -------------
`tmux` | Start a new session
`tmux ls` | List all sessions
`Ctrl` `b`, `d` | Detach from session
`tmux attach -t` | Re-attach a detached session 