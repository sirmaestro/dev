# dev

# Useful scripts
Generate Public/Private keys to ssh into server
```
ssh-keygen
cat ~/.ssh/id_rsa.pub | ssh USER@HOST "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
```

# Tmux
Command | Description
------------ | -------------
`tmux` | Start a new session
`tmux ls` | List all sessions
`Ctrl` `b`, `d` | Detach from session
`tmux attach -t` | Re-attach a detached session 