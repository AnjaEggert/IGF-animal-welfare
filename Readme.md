# IGF-animal-welfare

This repository contains data and source code to reproduce the data and statistical analysis and figures of the manuscript submitted to the journal "Scientific Reports":

Intertwining of the Igf system and animal welfare
by Anne-Marie Galow1, Daniela Ohde1, Anja Eggert1, Christina Walz1, Marianne Zenk1, Chaithra Umesh2, Saptarshi Bej3, Olaf Wolkenhauer2 and Andreas Hoeflich1

1Research Institute for Farm Animal Biology (FBN), Dummerstorf, Germany 
2University of Rostock, Dept. of Systems Biology and Bioinformatics, 18051 Rostock, Germany
3IISER Thiruvananthapuram, School of Data Science, 695551 Vithura, Kerala, India

## License

[![Creative Commons License](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

In order to reference this software, please consider the information in the [CITATION.cff](CITATION.cff) file.

## Usage

We run the data and statistical analysis on Windows 11. With one exception, all data processing, modeling and visualization is done in R.
Missing value imputation was done in Python.

R Core Team (2024). R: A Language and Environment for Statistical Computing. R Foundation for Statistical Computing, Vienna, Austria.
<https://www.R-project.org/>.

THE REPOSITORY CONTAINS:
1. Main folder with 5 quarto files and rendered reports in html
    + `igf-biomarker-summary-stats.qmd`: data processing, data summary statistics, processed data saved in "./data/data-processed.RData"
    + `igf-biomarker-models.qmd`: linear mixed models, generating figures, using `data-processed.RData`
    + `igf-biomarker-pca.qmd`: PCA and cluster analysis, using `data-processed.RData` and imputed data from `missing_value_imputation.ipynb`
    + `missing_value_imputation.ipynb`: Jupyter Notebook with kNN imputation in Python
    + `igf-confounder-age.qmd`: linear mixed model including age, supplements
    + `igf-confounder-boar.qmd`: linear mixed model including boars, supplements
3. Folder *data* with one xlsx-files:
    + `data-matrix.xlsx` with sheets:
      + `data_ori`: measured data
      + `data_ori_knn`: subset of variables used for kNN imputation
      + `data_imp`: imputed data set
      + `parameter description`: some meta information
4. Folder *plots* with 8 plots:
    + `figure3.png`: Effects of the husbandry system on cortisol and IGF bioactivity
    + `figure4.png`: Husbandry dependent IGF concentrations
    + `figure5.png`: Husbandry effects on regulators of IGF bioactivity 
    + `figure6.png`: Principal Component Analysis (PCA) of 15 candidate parameters related to husbandry systems
    + `ori-imp.png`: Comparison of data distributions for selected candidate parameters of the original and imputed data set, supplement
    + `figure-age.png`: Dependency of variables on insemination age, supplement
    + `figure-boar.png`: Conditions of litters depending on boar, supplement
