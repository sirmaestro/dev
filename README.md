# dev

# Useful commands
List 1st level of subdirectory size
```
sudo du -hc --max-depth=1 .
```

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

Unzip directory
```
unzip -o -d target_directory zip_file
```
Command | Description
------------ | -------------
`-l` | List contents of zip
`-d` | Unzip to target directory
`-o` | Overwrite existing files
`-u` | Update files
`-f` | Update only existing files
`-x` | Exclude files e.g. `-x *.srt`

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
example in relaxed environment (unraid), no enforcing permission or credientials
```
mount -t cifs -o rw,guest,noperm //192.168.1.2 /mnt/temp
```
# Tmux
Command | Description
------------ | -------------
`tmux` | Start a new session
`tmux ls` | List all sessions
`Ctrl` `b`, `d` | Detach from session
`tmux attach -t` | Re-attach a detached session 

# Git
Stashes changes, pulls from either the master or main branch, fetches updates from the remote, prunes remote-tracking branches, and finally prunes local branches that are no longer present on the remote.
```
/usr/bin/find . -maxdepth 1 -type d -print | parallel --eta 'echo {} && git -C {} stash && (git -C {} rev-parse --verify --quiet master && git -C {} checkout master || git -C {} checkout main) && git -C {} pull && git -C {} fetch -p && git -C {} remote prune origin && for branch in $(git -C {} branch -vv | grep ": gone]" | awk "{print \$1}"); do git -C {} branch -D $branch; done' \;
```
