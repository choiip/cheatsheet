# Docker

### Remove untagged images
> docker rmi $(docker images -f "dangling=true" -q)

### Remove stopped containers
> docker container prune

<!-- anchor -->

<center>
<br><br>
Copyright © 2017-2018 Alex Choi
</center>
