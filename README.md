TIPS
====
Remove all containers: docker rm `docker ps --no-trunc -a -q`
Overwrite entryponit and access docker: docker run -i -t --entrypoint="/bin/bash" -p 23:22 <image> -i
