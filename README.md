### Packages needed to run the script project.rmd  
I run this which newly created conda environment with python3
```
conda create -n Trinity-2.8.5 python=3.7 trinity=2.8.5 bioconductor-edger
conda activate Trinity-2.8.5
```
Other softwares you would need
- R  (>=3.5.1)
- pandoc  
- R package rmarkdown  
- trinity

export TRINITY_HOME="/path/to/trinity"

```
R -e "rmarkdown::render('project.Rmd',output_file='output.pdf')"
```
