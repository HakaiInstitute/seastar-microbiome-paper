The analyses and figures associated with this manuscript are broken into chunks based on the type of analysis being performed. 

The Rmd file 'smic_initialQC' draws on the original data files and turns them into a phyloseq object which is QC'ed and manipulated to obtain the final data set used in subsequent analyses. The package 'decontam' is used to detect contaminant ASVs based on negative controls. The three files required for this script are the taxonomy annotation file 'smic_runs1to8_silva138-1_taxonomy', the ASV table 'asvtable_NCM_smiconly-runs1to8' and the metadata file 'metadata_updated_2026' - all of these are located in the 'data' folder. *Note: smic_runs1to8_gg2_taxonomy was not used but is an alternative taxonomy file to smic_runs1to8_silva138-1_taxonomy. From this file I also saved two rds (phyloseq) objects which are called upon in subsequent scripts so that all these QC steps don't need to be repeated every time. These two files are 'decontam_filter_nonegs.rds' and 'decontam_filter_nonegs_prev.rds'. The latter file had just one extra step where rare taxa (present in <1% of samples) are filtered out.

A brief overview of all the R markdown files:

'field_density_prevalence.Rmd'
The R markdown also requires it's own data file, 'field_data_all' housed in the data folder. This script generates the density and wasting disease prevelance plots.

'smic_alpha_diversity.Rmd'
This Rmarkdown file draws upon one of the saved phyloseq objects and calculates alpha diversity (Inverse Simpson Index) across different variables (host, season, wasting categories). It also creates the plot 'alpha_host_boxplot' which is combined with the host NMDS plot in the beta_diversity script. We also used the packages stats, lme4, MuMIn and DHARMa packages to run the generalized linear models. 

'smic_beta_diversity.Rmd'
This Rmarkdown file draws upon the prevelance filtered phyloseq object and calculates beta diversity using the NMDS method based on Bray-curtis distances across different variables. It is also where the alpha diversity and beta diversity plots by host are combined into the multinpanel figure. We also used the vegan package here to run PERMANOVAs.

'smic_iris.Rmd'
This Rmarkdown file is used to create the iris plots of the top 12 classes of bacteria on each sea star species using the ord_plot_iris function within the MicroViz package.

'smic_taxa_barplots.Rmd'
This Rmarkdown file is used to identify the top 10 most abundant genera and create the stacked barplots across different variables with this top taxa.

'smic_core_microbiome.Rmd'
This Rmarkdown file is used to detect core microbial taxa for each sea star species using the core_members function within the microbiome package.

'smic_indispecies-intertidal.Rmd'
This Rmarkdown file is used to detect indicator taxa for each sea star species using the multipatt function in the indicspecies package.

'smic-compare-means.Rmd'
This Rmarkdown file was used to determine differentially abundant taxa across wasting disease categories and tissue types. We used the wilcox_test function with the rstatix package and also calculated logfold change among pairs of categories. 

'smic_vibrio.Rmd'
This Rmarkdown file is used to pull out ASVs that matched to Vibrio pectinicida, to plot it's relative abundance across hosts, wasting categories and through time.
