# jupyter-bash
Create executable demo scripts using a jupyter docker image and the bash kernel

This is useful for creating repeatable demo scripts with instructions

# build and name the image 
```bash
docker build -t jupyter/bash:1.1 ./docker
```

# Run the image from the directory you want to save the jupyter files
This example maps the demo directory in the docker image to the parent directory of the current folder.  I frequently have other repos at the same level as this demo repo - for example, sandbox infrastucture repos used to create demo environments.  This mapping makes those files available in the jupyter image.

```bash
docker run -p 8888:8888 -v $PWD/..:/home/jovyan/demo jupyter/bash:1.1
```

# Copy and open the URL as shown in the docker run output - it will look like this:
```
    To access the server, open this file in a browser:
        file:///home/jovyan/.local/share/jupyter/runtime/jpserver-7-open.html
    Or copy and paste one of these URLs:
        http://80c36ea9c3ff:8888/lab?token=7319d0e8a7fac42a368e74e1a133382de496142f78e263bf
        http://127.0.0.1:8888/lab?token=7319d0e8a7fac42a368e74e1a133382de496142f78e263bf
```
