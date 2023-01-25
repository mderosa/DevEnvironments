## Building
From this directory build the image with the command
```
docker build -t haskelldev .
```

## Post build
As the root user, set the password for user marco with the command
```
passwd marco
```
Then connect to a running container with vscode and install the vscode haskell dev tools. Be sure
