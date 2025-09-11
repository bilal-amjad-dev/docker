In this file, we have the commands that are used to write Dockerfile


`FROM`: Specifies the base image

`WORKDIR`: Sets the working directory

`RUN`: Runs Linux commands

`COPY`: Copy the code into container

`CMD`: Command to run your application




---


**FROM**

Specifies the base image to build upon. This is the starting point of your image.

Example: FROM ubuntu:20.04

**WORKDIR**

Sets the working directory inside the container. All subsequent instructions run relative to this directory.

Example: WORKDIR /app

**RUN**

Executes shell commands during image build. Typically used to install packages or setup the environment.

Example: RUN apt-get update && apt-get install -y curl

**COPY**

Copies files or directories from your local machine into the container’s filesystem.

Example: COPY ./src /app/src

**CMD**

Defines the default command to run when a container starts from the image. Only one CMD should be used; it can be overridden at runtime.

Example: CMD ["python3", "app.py"]




