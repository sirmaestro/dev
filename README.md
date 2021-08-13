# dev

# Useful scripts
Generate Public/Private keys to ssh into server
```
ssh-keygen
cat ~/.ssh/id_rsa.pub | ssh USER@HOST "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
```