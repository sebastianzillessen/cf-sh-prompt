
cf-sh-prompt
============

Show in the shell prompt where the Cloud Foundry CLI is currently pointing.

```
[vagrant:~/workspace/cf-sh-prompt]  (master) 
[MyOrganisation/Production] $
```

Currently tested on bash, with an aspiration to work in zsh.

In difference to the original idea of [bleach](https://github.com/bleach/cf-sh-prompt), this approach uses the `~/.cf/config.json` file of CloudFoundry, which makes this approach much more faster and reliable.

In addition, if a Space contains "Prod" it will color code the output with red background.

![Example](./terminal-cf-sh-prompt.png/?raw=true "Color coded output.")
 

Installing and using
====================

**Prerequisites**:
- `git` installed (or you need to adapt the `PW1` export)
- `jq` installed (e.g. use `sudo dnf install jq` or `sudo apt-get install jq`)
- Use the `cf` CLI at least once, so that the `.cf/config.json` file is created.

**Installation**:

```
wget -O ~/.cf-sh-prompt https://github.com/sebastianzillessen/cf-sh-prompt/raw/master/cf-sh-prompt
echo ". ~/.cf-sh-prompt" >> ~/.bashrc
```

As soon as you open now a new Tab in your shell you will find the following output:

```
CF Helper now installed.
[vagrant:~/workspace/het-composite/het]  (develop) 
[MyOrganisation/Space] $ 
```
As soon as the Space contains `Prod` it will color code the output with a red flag. 

Know Issues
====================

- As the `PS1` command includes `__git_ps1` the [git-prompt](https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh) needs to be installed on the running machine. 
