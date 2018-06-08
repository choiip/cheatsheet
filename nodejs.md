# NodeJS

## Install Node Version Manager (nvm)
### download install script and run
> curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
### update ~/.bash_profile
```
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.bash_profile &&
echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"' >> ~/.bash_profile
```
### List available version of NodeJS for install
> nvm ls-remote 

### List the installed versions of NodeJS
> nvm ls

## Install NodeJS 
### Install NodeJS through nvm
> nvm install v8.11
### Query for current version
> node -v

## Configure registry (Optional)
> npm config get registry

> npm config set registry http://[your-server]:[port]/artifactory/npm



<!-- anchor -->

<center>
<br><br>
Copyright © 2017 Alex Choi
</center>
