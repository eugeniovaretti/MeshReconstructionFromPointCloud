# Mesh reconstruction from point cloud
This repository contains the final project of Computing Tools for Scientific Programming course a.y 2022/2023 for the MSc. Mathematical Engineering, Politecnico di Milano.  

# Installation

## For end users
The repository contains as module the `Open3D` library, a C++ library for building meshes from point clouds.

Since one of the goal of this project was to improve Open3D original performances, you will need to install from source the modified library - a pull request to the Open3D library has not been made yet :) .

**Clone the repository**:  
To install and use the repository properly, please `cd` to the folder you wish to install it, and clone it through the following command-line instructions:

```shell
git clone --recursive https://github.com/SimonePiazza99/Project3-Mesh_Surface
```
or

```shell
git clone --recursive git@github.com:SimonePiazza99/Project3-Mesh_Surface.git
```
In the latter case you have to register your ssh keys on a github account.





## How to build `Open3D`

**Prerequisites**: To build `Open3D`, please refer to the [Open3D compilation guide](http://www.open3d.org/docs/release/compilation.html) to check system requirements.

Below you can find an extract of this guide for Ubuntu (it may not work for all machines!).  

If requirements are satisfied browse to `Open3D`. On Linux machines, it is sufficient to run  
```shell
 cd Open3D
```
**Install dependencies and activate you virtual enviroment**
```shell
# Only needed for Ubuntu
util/install_deps_ubuntu.sh
```

Then, activate your conda enviroment
```shell
conda activate your_env_name
```

**Config**
```shell
mkdir build
cd build/
cmake ..
```

**Build**
```shell
sudo make
```
or if you want to speed up the process:

```shell
# On Ubuntu
sudo make -j$(nproc)
```

**Install**
To install C++ library
```shell
sudo make install
```
To install Open3D Python library:
```shell
# Activate the virtualenv first
# Install pip package in the current python environment
sudo make install-pip-package
```

Finally verify the installation with:
```shell
python -c "import open3d"
```

# Reproducibility  
This section is intended for any user who wants to run the analysis to reproduce the same results, or for any user who wants to analyze results with different hyperparameter values (in particular, the penalization parameter (`lambda`) and the angle treshold (`cos_alpha`) ), or for those who want to apply the same procedure to their own point-cloud.  
The repository is structured as follow:
- `Open3D` : contains the submodule that performs the mesh reconstructon.  
- `data` : contains all the input data.  
- `output` : contains simulation useful for presentation/report.
- `dcode`: contains code written during development.

In the repo lot of scripts are at disposal. Worth to notice is `test_o3d.ipynb` that allows a fast analysis of results.


# Authors  
- Piazza Simone ([@SimonePiazza99](https://github.com/SimonePiazza99))
- Valentini Federica ([@federicavalentini99](https://github.com/federicavalentini99))
- Varetti Eugenio ([@eugeniovaretti](https://github.com/eugeniovaretti))

# Only for "interested" users  
To download Open3D 's updates type
```shell
cd Open3D
git pull origin master
cd ..
```
If there are updates, after having verified that your working tree is clean ('git status' to check) do:
```shell
git add Open3D
git commit -m "Downloaded Open3D updates"
git push
```
