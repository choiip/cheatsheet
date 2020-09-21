# Docker

### Remove untagged images
> docker images | grep none | awk '{ print $3; }' | xargs docker rmi

### Remove dangling images
> docker rmi $(docker images -f "dangling=true" -q)

### Remove stopped containers
> docker container prune

<!-- anchor -->

<center>
<br><br>
Copyright © 2017-2018 Alex Choi
</center>
