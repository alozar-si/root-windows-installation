# Tutorial for ROOT and pyroot installation on Win10

## Installation

### prerequisite

Select the desired ROOT version and choose the correct Windows Visual Studio

1. Download and install Windows Visual Studio
2. Anaconda or venv

### Install root x64 / x32

1. Download ROOT: `https://root.cern/install/all_releases/`
    1. Example: `root_v6.32.08.win64.vc17.exe` needs `Windows Visual Studio 2022 64-bit x64`
2. Install Windows Visual Studio 2022
    1. Install "Desktop development for Windows with C++"
3. Install root
3. (Optional) Put `C:\root_v###\bin` to PATH
4. Setup Python environment for pyroot (optional 32bit)
    1. `set CONDA_FORCE_32BIT=1` (optional)
    2. `conda create -n pyroot_env python=3.11.7` 
        1. choose a compatible python version, see [Troubleshooting 1.](#Troubleshooting)

### Install PyRoot in jupyter notebook

1. Open pyroot environment (ex. myPyRootEnv)
2. `conda install -c anaconda ipykernel notebook`
3. `python -m ipykernel install --user --name=myPyRootEnv`
4. Run `jupyter notebook` and open notebook
5. Select correct kernel: Kernel->Change kernel->myPyRootEnv

## Usage

### Running root

1. If you installed ROOT to C:\root then call C:\root\bin\thisroot.bat before using ROOT to set up required environment variables.
2. If you set root to PATH, then just call root

### Running pyroot

1. Start env `conda activate pyroot_env`
2. Source ROOT:
    1. call `C:\root\bin\thisroot.bat` before using pyroot **OR**
    2. source in python script: `import sys; sys.path.append("C:\\root_v6.26.10\\bin")`
5. In python: `import ROOT`

## Troubleshooting

1. Failed importing DLL libcppyy___(version): 
    1. Check python version (`root-config --python3-version`) if it is compatible with the installed root (ex: 6.26/06 needs python 3.8.2).
    2. [Link to the issue on root-forum](https://root-forum.cern.ch/t/some-problem-about-pyroot/44971)

## References

1. https://medium.com/@nrk25693/how-to-add-your-conda-environment-to-your-jupyter-notebook-in-just-4-steps-abeab8b8d084

# Linux
1. Install `ROOT` from [precompiled binaries](https://root.cern/install/#download-a-pre-compiled-binary-distribution) and follow the installation procedure
2. If missing libraries, use apt-file
3. Install `pyenv`
4. Install correct python version using `pyenv install X.X.X`
5. Activate python `pyenv local X.X.X` or `pyenv global X.X.X`
