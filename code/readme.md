The analyses and figures associated with this manuscript are broken into chunks based on the type of analysis being performed. 

The Rmd file 'smic_initialQC' draws on the original data files and turns them into a phyloseq object which is QC'ed and manipulated to obtain the final data set used in subsequent analyses. The three files required for this script are the taxonomy annotation file 'smic_runs1to8_silva138-1_taxonomy', the ASV table 'asvtable_NCM_smiconly-runs1to8' and the metadata file 'metadata_updated_2026' - all of these are located in the 'data' folder. *Note: smic_runs1to8_gg2_taxonomy was not used but is an alternative taxonomy file to smic_runs1to8_silva138-1_taxonomy


'field_density_prevalence.Rmd'
The R markdown also requires it's own data file, 'field_data_all' housed in the data folder. This script generates the density and wasting disease prevelance plots.
