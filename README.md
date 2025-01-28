# Conda

Anaconda can be downloaded [here](https://www.anaconda.com/download/success).  
[Cheat sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

## Basics
Conda manages environments, allowing users to seamlessly switch between
multiple installations of your programming language of choice along with required dependencies.

This removes the need to have one bloated, monolithic environment for all of your projects. This is especially important if your projects have
varying dependencies or require specific versions of packages.

## Pros and Cons:
### Pros:
- Straightforward package manager that is widely used in nearly all research institutions / teaching
- Rich ecosystem of packages across various channels
- Bundles dependencies of complex packages very effectively. (e.g. `cuda-toolkit`)

### Cons:
- Can be very slow: resolving dependencies can be very time-consuming
- Suboptimal choice for deployment
- Environments can get bloated quickly

## Getting started
1. Create a new blank environment:
```bash
conda create --name py312 python=3.12
```
2. Activate the environment:

Linux:
```bash
source activate py312
```

Windows:
```bash
activate py312
```

3. Install packages (basic)
```bash
conda install jupyter
```

4. Install packages from other channels (e.g. `conda-forge`)
```bash
conda install conda-forge::scikit-image
```

