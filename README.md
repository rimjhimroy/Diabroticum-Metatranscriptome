### Packages needed to run the script project.rmd  
I run this which newly created conda environment with python3
```
conda config --add channels conda-forge
conda config --add channels defaults
conda config --add channels r
conda config --add channels bioconda
conda create -n Trinity-2.8.5 python=3.7 trinity=2.8.5 bioconductor-edger=3.24.3 bioconductor-deseq2=1.22.1 bioconductor-limma=3.38.3 bioconductor-ctc=1.58.0 bioconductor-biobase=2.42.0
conda activate Trinity-2.8.5
cd $CONDA_PREFIX
mkdir -p ./etc/conda/activate.d
mkdir -p ./etc/conda/deactivate.d
touch ./etc/conda/activate.d/env_vars.sh
touch ./etc/conda/deactivate.d/env_vars.sh
cat <<EOF > ./etc/conda/activate.d/env_vars.sh
#!/bin/bash
export OLD_LD_LIBRARY_PATH=${LD_LIBRARY_PATH}
export LD_LIBRARY_PATH=${CONDA_PREFIX}/lib:${LD_LIBRARY_PATH}
export TRINITY_HOME=${CONDA_PREFIX}/opt/trinity-2.8.5
EOF
cat <<EOF > ./etc/conda/deactivate.d/env_vars.sh
#!/bin/bash
export LD_LIBRARY_PATH=${OLD_LD_LIBRARY_PATH}
unset OLD_LD_LIBRARY_PATH
EOF

```
Other softwares you would need
- pandoc `conda install -c conda-forge pandoc`  
- R package rmarkdown `conda install r-rmarkdown r-tinytex`    
- R package venndiagram, gplot, here `conda install r-venndiagram r-gplots r-here`


```
R -e "rmarkdown::render('project.Rmd',output_file='output.pdf')"
```
