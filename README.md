# Python in Docker

Easy method for deploying your Python application in a Docker container.

[![](https://images.microbadger.com/badges/image/godatadriven/python-onbuild.svg)](https://microbadger.com/images/godatadriven/python-onbuild "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/godatadriven/python-onbuild.svg)](https://microbadger.com/images/godatadriven/python-onbuild "Get your own version badge on microbadger.com") 

## Extending the container

Make sure your requirements.txt in located in the current working directory.
Moreover, by default the container will start main.py.

```
FROM godatadriven/python-onbuild
COPY /app /app
```