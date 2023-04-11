```
mamba create -n ece python=3.10
conda activate ece
cd ~/projects/ece/ece-env
conda env export > environment.yml
poetry install
```