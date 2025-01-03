# Use Ubuntu latest as the base image
FROM ubuntu:latest

# Set environment variables to prevent interactive prompts during package installations
ENV DEBIAN_FRONTEND=noninteractive
ENV PATH /opt/conda/bin:$PATH

# Install required system dependencies
RUN apt-get update && apt-get install -y \
    wget \
    bzip2 \
    git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# # Install Miniconda
# RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-aarch64.sh -O /tmp/miniconda.sh && \
#     bash /tmp/miniconda.sh -b -p /opt/miniconda && \
#     rm /tmp/miniconda.sh && \
#     /opt/miniconda/bin/conda clean -a -y

# # Set PATH to include Miniconda
# ENV PATH="/opt/miniconda/bin:$PATH"

# # Copy the environment.yml file to the container
# COPY environment.yml /tmp/environment.yml

# # Create the Conda environment and clean up
# RUN conda env create -f /tmp/environment.yml && \
#     conda clean -a -y && \
#     rm /tmp/environment.yml

# # Set default shell to bash and activate the environment
# RUN echo "conda activate nyc_airbnb_dev" >> ~/.bashrc

# Set the default command to start a shell
CMD ["bash"]


# FROM mcr.microsoft.com/devcontainers/anaconda:1-3

# # Copy environment.yml (if found) to a temp location so we update the environment. Also
# # copy "noop.txt" so the COPY instruction does not fail if no environment.yml exists.
# COPY environment.yml* .devcontainer/noop.txt /tmp/conda-tmp/
# RUN if [ -f "/tmp/conda-tmp/environment.yml" ]; then umask 0002 && /opt/conda/bin/conda env update -n base -f /tmp/conda-tmp/environment.yml; fi \
#     && rm -rf /tmp/conda-tmp

# # [Optional] Uncomment this section to install additional OS packages.
# # RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
# #     && apt-get -y install --no-install-recommends <your-package-list-here>
