#Bootstrap: localimage
#From: ./sherpa.sif
Bootstrap: shub
From: timo-singularity/sherpa

%help

  Container with Rivet, Sherpa, Pytorch

%post

  yum -y install git
  
  pip3 --no-cache-dir install cython numpy scipy
  pip3 --no-cache-dir install torch torchvision
  pip3 --no-cache-dir install matplotlib pandas seaborn
  pip3 --no-cache-dir install ipykernel jupyterlab
  
  pip3 --no-cache-dir install numdifftools nflows
  pip3 --no-cache-dir install gvar
  git clone https://gitlab.com/tjansse/vegas.git
  pip3 install ./vegas

   # we need to downgrade jedi, as there is a problem with auto-completion
  # in the current jupyter
  pip3 --no-cache-dir install --upgrade --force-reinstall jedi==0.17.2

  ldconfig
  yum clean all
