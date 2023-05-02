# Notes in a Life of a Developer
My notes along the daily trouble of a developer. For me and the public community.

## SSH Key in Github
1. Generate a local ssh-key: `ssh-keygen -t ed25519` or `ssh-keygen`
  - Enter unique *path* and *filename* for the the key. eg. `~/.ssh/foo`
2. Add new key to ssh-agent: (eg. with *GitBash* or *Terminal*)
  - command for starting ssh-agent:`ssh-agent -s`
  - command for adding new ssh-key to agent: `ssh-add ~/.ssh/foo`
3. Add Key to Github:
  - Copy content of *ssh-file.pub* eg. `~/.ssh/foo.pub`
  - Generate a new ssh-key in settings of github
  - Give according key-name (eg. foo) and paste the content of the *ssh-file.pub*
4. Check:
  - basic git functions (clone, pull, push)
  - check for signed key in ssh-agent: `ssh-add -l -E sha256`
  - check for signed key in github: `ssh -vT git@github.com`
5. Still trouble?
  - try to configure a *config*-file in the *~/.ssh*-path with content as follows:
  (eg. for foo)
  - now its time for giyf
```
Host github.com
 HostName github.com
 User yourGithubName
 IdentityFile ~/.ssh/foo
```
