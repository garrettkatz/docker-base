# docker-base
A template for version-controlled docker images with some python libraries.

Build the image: In the top-level of the repository run

`$ docker build -f ./docker/Dockerfile -t="docker-base" .`

Check the Dockerfile to see what happens when you build.  To run the image you built in a container:

`$ docker run -it --rm docker-base`

From inside the container, try running a python script:

`# python src/hello.py`

If it's working, you should see a message about the torch version.  When you're ready to quit the container:

`# exit`

If you are modifying some code in `src` on your host machine (outside of the container), and then want to test your modifications by running the code within the container, but don't want to wait to re-build the image:

`docker run -it --rm -v /full/path/to/docker-base/src/:/src docker-base`


