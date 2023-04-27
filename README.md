On e.g. `tononi-2`:

1. Install mambaforge
```
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-$(uname)-$(uname -m).sh"
bash Mambaforge-$(uname)-$(uname -m).sh
```
2. Install poetry version 1.3.1 (to avoid keyring issues with latest version)
```
curl -sSL https://install.python-poetry.org | python3 - --version 1.3.1
```
3. Clone all the repositories you will need:
```
mkdir ~/projects/ece/
cd ~/projects/ece/
git clone https://github.com/grahamfindlay/ece-env.git
git clone https://github.com/CSC-UW/ecephys.git
git clone https://github.com/CSC-UW/wisc_ecephys_tools.git
git clone https://github.com/CSC-UW/spikeinterface.git
# These following repositories are really not essential, but you might as well
git clone https://github.com/CSC-UW/discoflow.git
git clone https://github.com/grahamfindlay/seahorse.git
```
4. Install
```
mamba create -n ece python=3.10 pyqt
mamba activate ece
cd ~/projects/ece/ece-env
pip install sortednp --no-deps
poetry install
```