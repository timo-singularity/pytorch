#Bootstrap: localimage
#From: ./sherpa.sif
Bootstrap: shub
From: timo-singularity/sherpa

%help

  Container with Rivet, Sherpa, Pytorch

%runscript

  source /conda/etc/profile.d/conda.sh
  conda activate pytorch

%post

  yum -y install git
  
  wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.9.2-Linux-x86_64.sh -O miniconda.sh
  bash miniconda.sh -b -p conda
  source /conda/etc/profile.d/conda.sh
  conda update -y -n base conda
  conda create -y -c pytorch -c conda-forge -n pytorch cython numpy scipy pytorch torchvision torchaudio cudatoolkit=11.1 matplotlib pandas seaborn ipykernel jupyterlab numdifftools joblib
  rm miniconda.sh -f
  pip --no-cache-dir install nflows gvar
  git clone https://gitlab.com/tjansse/vegas.git
  pip install ./vegas

  ldconfig
  yum clean all
