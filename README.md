*Updated 11/19/2024.*
On e.g. `tononi-2`:

1. Install miniforge
```
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh
```
2. Clone all the repositories you will need:
```
mkdir ~/projects/ece/
cd ~/projects/ece/
git clone https://github.com/grahamfindlay/ece-env.git
git clone https://github.com/CSC-UW/spikeinterface.git # Be mindful of branch. You may want wisc/dev. Unfortunate we cannot use upstream spikeinterface[full] without significant refactoring.
git clone https://github.com/CSC-UW/ephyviewer.git # You may be able to get away with just the PyPI version of this.
git clone https://github.com/CSC-UW/kCSD-python.git # Can hopefully just use PyPI version once scipy.integrate.simpson is used
git clone https://github.com/CSC-UW/ecephys.git
git clone https://github.com/CSC-UW/wisc_ecephys_tools.git
# These following repositories are really not essential, but you might choose to install one (or both) of them.
git clone https://github.com/grahamfindlay/seahorse.git
git clone https://github.com/CSC-UW/discoflow.git
```
3. Install
```
cd ~/projects/ece/ece-env
mamba create -n ece python=3.12 # The bottleneck is currently numba, which as of 11/19/2024 does not support python 3.13 (but should by the end of the year).
mamba env update -n ece -f environment.yml
mamba activate ece
```
You might need PySide6 + Qt6 for ephyviewer:
```
pip install PySide6
```