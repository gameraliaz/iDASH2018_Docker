# Use a base image of your choice (e.g., Ubuntu)
FROM ubuntu:latest

# Install necessary dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    libgmp-dev \
    libmpfr-dev \
    libmpc-dev \
    make \
    gcc 

# Copy the NTL source tarball to the container
COPY ntl-10.3.0.tar.gz /ntl-10.3.0.tar.gz

# Extract and build the NTL library
RUN tar -xzf /ntl-10.3.0.tar.gz -C / \
    && cd /ntl-10.3.0/src \
    && ./configure ENV NTL_THREAD_BOOST=on \  
    && make \
    && make check \
    && make install 

# Clean up
RUN rm -rf /ntl-10.3.0.tar.gz

# Optionally, you can specify a command to run when a container is started
CMD ["/bin/bash"]
