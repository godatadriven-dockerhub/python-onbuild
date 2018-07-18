# Python in Docker

Easy method for deploying your Python application in a Docker container.

[![](https://images.microbadger.com/badges/image/godatadriven/python-onbuild.svg)](https://microbadger.com/images/godatadriven/python-onbuild "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/godatadriven/python-onbuild.svg)](https://microbadger.com/images/godatadriven/python-onbuild "Get your own version badge on microbadger.com") 

## Using/Extending the container

We've created two containers which allow you to easily create docker containers for Python programs.
The default image is based around pip and will copy/install your requirements.txt file in the container at build time.

Make sure your requirements.txt in located in the current working directory.

```
FROM godatadriven/python-onbuild:pip
COPY /app /app
```

The other container (with the conda tag), is similar but uses an environment.yml file.

```
FROM godatadriven/python-onbuild:conda
COPY /app /app
```

### Examples
Go to the example-usage folder to find an example of both containers