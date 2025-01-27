# Docker

### Installation options
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) (recommended for beginners)
- [Using `apt`](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
- [Manual installation](https://docs.docker.com/engine/install/ubuntu/#install-from-a-package)
- [Convenience script](https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script)

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh --dry-run
```

Remove the `--dry-run` option after a successful run.

### Verify installation
```bash
docker run hello-world
```

A basic example:
Running a jupyter server in docker

```bash
docker run -i -t -p 8888:8888 continuumio/anaconda3 /bin/bash -c "\                            
    conda install jupyter -y --quiet && \
    mkdir -p /opt/notebooks && \
    jupyter notebook \
    --notebook-dir=/opt/notebooks --ip='*' --port=8888 \
    --no-browser --allow-root"
```

Building a Docker container from scratch:
We need an `environment.yaml`:

```yaml
name: myenv

dependencies:
  - python=3.12
  - numpy
  - jupyter
  - matplotlib
  - pandas
```
Advanced: Can you spot issues with this environment?

And we need a Dockerfile:

```Dockerfile
FROM continuumio/anaconda3:2024.10-1

COPY environment.yaml environment.yaml
RUN conda env create --name my_env --file=environment.yml
RUN conda activate my_env

```

### GPU support
Standard docker run: e.g. `--gpus=all`  
Docker compose:
```yaml
deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
```

