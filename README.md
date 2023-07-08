# PanelApp Gene Enrichment

This script retrieves genetic panel data from PanelApp (https://panelapp.genomicsengland.co.uk) and performs gene enrichment analysis using a Fisher's exact test. The results are visualized using a volcano plot. The significant results are saved as a CSV file.

## Usage

Simply run the notebook `panel_app_gene_enrichment.ipynb` in Google Colab or Jupyter.

## Required Libraries

The script requires the following Python libraries:

- pandas
- requests
- matplotlib
- numpy
- scipy

These can be installed via pip using `pip install pandas requests matplotlib numpy scipy`.

## Steps

1. **Data Retrieval**: The script fetches all panels from PanelApp using the PanelApp API. For each panel, the script fetches the associated genes that have a confidence level of 3.

2. **Data Processing**: The retrieved genes are stored in a DataFrame and saved to a CSV file (`genes.csv`).

3. **Enrichment Analysis**: The script performs a Fisher's exact test for each panel against a set of rhythmic genes loaded from a URL. The results are stored in a DataFrame with the panel ID, panel name, odds ratio, and p-value.

4. **Data Visualization**: The script creates a volcano plot from the results of the Fisher's exact test, with the log odds ratio on the x-axis and the -log10 p-value on the y-axis. Points are colored red if the p-value is not significant (>= 0.05), and blue if the p-value is significant (< 0.05).

5. **Data Saving**: The results of the Fisher's exact test are saved to a CSV file (`fisher_results.csv`). The significant results are also saved separately (`significant_fisher_results.csv`).

## Customization

If you wish to use a different set of genes for the Fisher's exact test, modify the `dataset_url` variable in the script.

The confidence level for the gene retrieval can be adjusted in the `get_genes_for_panel` function. Adjust the `confidence_level` parameter as needed.

## Future Development

This script provides a foundation for genetic enrichment analysis and can be extended as needed. Possible future developments include adding further statistical tests, using different sets of genes for comparison. This repo will be updated if the panel app APIs for genetic data retrieval are altered by Genomics England

## Contact

For any further questions, please open an issue on GitHub. 
