# Genomix

A Python tool for visualizing the GC content landscape of a DNA/RNA sequence. It retrieves a GenBank record from NCBI by accession ID, calculates GC percentage across fixed-size windows, and produces a publication-style report figure.

## What it does

- Fetches a nucleotide record from NCBI (GenBank format) using Biopython's `Entrez` and `SeqIO`
- Calculates GC percentage in non-overlapping windows (default: 200 bp)
- Plots the GC density profile along the sequence
- Adds a heatmap of sequence composition for a quick overview of GC-rich and GC-poor regions
- Saves the figure as a high-resolution PNG (`professional_genomic_report.png`, 300 dpi)

## Example

The notebook runs the analysis on `NM_007294` (human *BRCA1* transcript) as a demonstration. Any valid NCBI nucleotide accession ID can be used instead.

## Requirements

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- biopython

```bash
pip install pandas numpy matplotlib seaborn biopython
```

## Usage

1. Open `Genomix-Core.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.
2. Replace the email address with your own (NCBI requires a contact email for Entrez requests).
3. Change the accession ID if you want to analyze a different sequence.
4. Run the cell.

```python
visualizer = AdvancedGenomicVisualizer("your_email@example.com")
if visualizer.fetch_data("NM_007294"):
    visualizer.plot_genomic_landscape()
```

## Project structure

| Component | Description |
|---|---|
| `AdvancedGenomicVisualizer` | Main class: data retrieval and plotting |
| `fetch_data()` | Downloads and parses the GenBank record from NCBI |
| `get_gc_distribution()` | Computes GC % per window |
| `plot_genomic_landscape()` | Generates the line plot and heatmap, saves the PNG |

## Limitations and future work

- Currently supports a single sequence per run
- Window size is fixed at the default value unless changed in code
- Planned: annotation overlays (exons, CDS), multi-sequence comparison, and export of GC statistics as CSV

## Author

Kifayat Aliyeva  
MBA (AI & Business) student, UNEC. Interested in bioinformatics and data analytics.  
[LinkedIn](https://www.linkedin.com/in/kifayat-aliyeva)
