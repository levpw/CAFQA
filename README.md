# CAFQA

(Re-)Implementation of an interface for the Variational Quantum Eigensolver and the [CAFQA](https://dl.acm.org/doi/abs/10.1145/3567955.3567958) scheme (original code: https://github.com/rgokulsm/CAFQA).

CAFQA is a special case of VQE where the ansatz is built of Clifford gates only and the optimization is therefore performed over a discrete set. This implementation uses [Stim](https://github.com/quantumlib/Stim) for fast Clifford circuit simulation and [HyperMapper](https://github.com/luinardi/hypermapper) for Bayesian Optimization over the discrete search space.

Full list of dependencies (`pip install ...`):
- numpy
- qiskit
- qiskit[optimize]
- qiskit[nature]
- stim
- scikit-quant
- hypermapper
- pyscf

## Create a conda environment if you have not already:

```
conda create --name qs-01 python=3.12.2 -y
```

## Activate the environment:

```
conda activate qs-01
```

## Install the necessary libraries.

```
pip install -r requirements.txt
```

## start docker container and run your code there
in native terminal run
```
docker build -t image_name .
docker run --platform linux/amd64 -it --rm image_name
```

then in the docker image run necessary commands such as
```
conda env create -f environment.yml
conda activate mycondaenv
cd ./example/H2/
python h2.py
```