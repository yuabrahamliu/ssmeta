# ssmeta

This program is used to do the metagene analysis on the ssRNA-seq and Pro-seq data.

## Usage

If you want to start the analysis from bam files, you need to first put the files in the folder "data" in the package, then configure the parameters in the config file, and finally, simply type `make`, then the program will run automatically.

## Parameters 

* countreads - If your analysis is from bam files, give "Yes" to this parameters, otherwise, "No".
* pos_f - It is the path where the genelist containing the genes to be analyzed is.
* result_tag - It is a part of the name of count result file. The format is "data number1_data number2_analyzed gene type", for example, "bd12_19_lnc".
* width1 - The TSS upstream region length need to be counted
* width2 - The TTS downstream region length need to be counted
* ssmethod - The strand specific method, directional_ligation or dUTR
* drawfig - If you just want to count the reads and don't want to draw the metagene plot, set it as "No". If you want to get the plot, set to "Yes".
* fig_tag - It's the label of the count file need to be converted to metagene plot and is a part of the count file name. For example, "bd12_19". The count files generated by the count step of this program will automatically stored in the "result" folder and will be converted to plot if you choose "Yes" on the drawfig parameter. However, it is not necessary to start from the read count step every time. If you already have count files and just want to plot them directly, you can set the countreads parameter to "No", then put the count files in the "result" folder and the program will recognize them to draw the plot.
* halfwindow - For example, if you set 1000 here, the up and downstream of 1000bp around TSS (both sense and antisense strands) and around TTS (only sense strand) will be plotted. Can use more than 1 numbers here, just need to separate them with comma, like 2000,1000,500 
* sampletags - To label the experimental condition of the data and write them to the figure legend, set them here and separate with comma. Note that the order of these condition names should be the same as the order of the count result file names. An example is, +dox_4d_rep1,-dox_4d_rep1,+dox_4d_DRB_5min_rep1,-dox_4d_DRB_5min_rep1,+dox_4d_DRB_15min_rep1,-dox_4d_DRB_15min_rep1,+dox_4d_DRB_30min_rep1,-dox_4d_DRB_30min_rep1
