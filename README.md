# Python in Docker

Easy method for deploying your Python application in a Docker container.

[![](https://images.microbadger.com/badges/image/godatadriven/python-onbuild.svg)](https://microbadger.com/images/godatadriven/python-onbuild "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/godatadriven/python-onbuild.svg)](https://microbadger.com/images/godatadriven/python-onbuild "Get your own version badge on microbadger.com") 

## Using/Extending the image

We've created two containers which allow you to easily create Docker containers for Python programs.
The default image is based around pip and will copy/install your requirements.txt file in the image at build time.

Make sure your `requirements.txt` in located in the current working directory.

```
FROM godatadriven/python-onbuild:pip
COPY /app /app
```

The other image (with the conda tag), is similar but uses an `environment.yml` file.

```
FROM godatadriven/python-onbuild:conda
COPY /app /app
```

## Debian packages

On top of Python dependencies, you might have a requirement to install additional Debian packges in your Docker container.
You can do this by placing a `packages.txt` file in the root of your project. 
If this file is present, we will use apt to install them. 

### Examples
Go to the example-usage folder to find an example of both containers