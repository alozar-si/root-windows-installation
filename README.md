# Tutorial for ROOT and pyroot installation on Win10

## Installation

### Prerequests

Select desired ROOT version and choose correct Windows Visual Studio

1. Download and install Windows Visual Studio
2. Anaconda or venv

### Install

1. Download ROOT: `https://root.cern/install/all_releases/`
    1. Example: `root_v6.26.06.win32.vc17.exe` needs `Windows Visual Studio 2022 32-bit x86`
2. Install root
3. (Optional) Put `C:\root_v###\bin` to PATH
4. Setup python environment for pyroot 32bit
    1. `set CONDA_FORCE_32BIT=1`
    2. `conda create -n pyroot_env python=3.8.2` 
        1. choose compatible python version, see [Troubleshooting 1.](#Troubleshooting)

## Usage

### Running root

1. If you installed ROOT to C:\root then call C:\root\bin\thisroot.bat before using ROOT to set up required environment variables.
2. If you set root to PATH, then just call root

### Running pyroot

1. Start env `conda activate pyroot_env`
2. call `C:\root\bin\thisroot.bat` before using pyroot
3. In python: `import ROOT`

## Troubleshooting

1. Failed importing DLL libcppyy___(version): 
    1. Check python version (`root-config --python3-version`) if is compatible with installed root (ex: 6.26/06 needs python 3.8.2).
    2. [Link to the issue on root-forum](https://root-forum.cern.ch/t/some-problem-about-pyroot/44971)
