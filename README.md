### Packages needed to run the script project.rmd  
I run this which newly created conda environment with python3
```
conda create -n Trinity-2.8.5 python=3.7 trinity=2.8.5 bioconductor-edger 
conda activate Trinity-2.8.5
export TRINITY_HOME=$CONDA_PREFIX
```
Other softwares you would need
- pandoc  
- R package rmarkdown `conda install -c r r-rmarkdown`    

export TRINITY_HOME="/path/to/trinity"

```
R -e "rmarkdown::render('project.Rmd',output_file='output.pdf')"
```
