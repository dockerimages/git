### dockerimages/git:alpine

[![DockerHub Badge](http://dockeri.co/image/alpine/git)](https://hub.docker.com/r/dockerimages/git/)

### usage

    docker run -ti --rm -v ${HOME}:/root -v $(pwd):/git dockerimages/git:alpine <git_command>

For example, if you need clone this repository, you can run

    docker run -ti --rm -v ${HOME}:/root -v $(pwd):/git dockerimages/git clone https://github.com/dockerimages/git.git
    
### Optional usage 1:

To save your typeing, add this fuction to `~/.bashrc` or `~/.profile`
    
    $ cat ~/.profile
    
    ...
    
    function git () {
        (docker run -ti --rm -v ${HOME}:${HOME} -v $(pwd):/git dockerimages/git:alpine "$@")
    }
    
    ...
    
    $ source ~/.profile

for example, if you need clone this repository, with the function you just set, you can run it as local command

    git clone https://github.com/dockerimages/git.git

### Optional usage 2:

    alias git="docker run -ti --rm -v $(pwd):/git -v ${HOME}:${HOME} dockerimages/git:alpine
    
#### NOTES:

- You need redefine (re-run) the alias, when you switch between different repositories
- You need run above alias command only under git repository's root directory.
