# Docker Installation

## Install Docker
- Update existing list of packages
``` zsh
apt update
```

- Install a few prerequisite packages which let apt use packages over HTTPS
``` zsh
apt install apt-transport-https ca-certificates curl software-properties-common
```

- add the GPG key for the official Docker repository to system
``` zsh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

- Add the Docker repository to APT sources
``` zsh
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

- If Ubuntu's version is 22.04
``` zsh
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu jammy stable"
```

- Check Docker repo, it will show output of apt-cache policy docker-ce
``` zsh
apt-cache policy docker-ce
```

- Install
``` zsh
apt install docker-ce
```

- Check version
``` zsh
docker version
```

- Check Docker status
``` zsh
systemctl status docker
```

---
## References
How To Install and Use Docker on Ubuntu 20.04  
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04
