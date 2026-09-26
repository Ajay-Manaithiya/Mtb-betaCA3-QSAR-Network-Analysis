# Mtb-betaCA3-QSAR-Network-Analysis

## ML-QSAR and network analysis of Mtb β-CA3 modulators

This repository contains the data, code, and results used for the ML-QSAR and network analysis of small-molecule modulators of *Mycobacterium tuberculosis* β-carbonic anhydrase 3 (β-CA3; Rv3273).

### Public repository

[Mtb-betaCA3-QSAR-Network-Analysis](https://github.com/Ajay-Manaithiya/Mtb-betaCA3-QSAR-Network-Analysis.git)

---

### Activity transformation

For a Ki value of `x` in nM:

```text
pKi = 9 - log10(x)
```

---

Target Protein Sequence

The amino-acid sequence and basic annotation of Rv3273 (β-carbonic anhydrase 3) from Mycobacterium tuberculosis H37Rv can be accessed from the following resources:

MycoBrowser – Rv3273: https://mycobrowser.epfl.ch/genes/Rv3273

UniProt – P96878: https://www.uniprot.org/uniprotkb/P96878/entry

The protein sequence used in this study was obtained from these curated database resources.

---

### ML-QSAR analysis

The dataset contained 101 compounds from ChEMBL target CHEMBL5767. PaDELPy was used to calculate 1,444 one- and two-dimensional descriptors and 307 binary fingerprints. Constant, low-variance, and highly correlated features were removed.

The data were divided into training and test sets in an 80:20 ratio. Random Forest regression was applied using the following default settings:

```text
n_estimators = 100
criterion = squared_error
max_depth = None
min_samples_split = 2
min_samples_leaf = 1
min_weight_fraction_leaf = 0.0
max_features = 1.0
max_leaf_nodes = None
min_impurity_decrease = 0.0
bootstrap = True
oob_score = False
n_jobs = None
random_state = None
verbose = 0
warm_start = False
ccp_alpha = 0.0
max_samples = None
```

The train/test settings were `test_size=0.20`, `shuffle=True`, `stratify=None`, and `random_state=None`. Five-fold and ten-fold cross-validation were performed without fold shuffling. No fixed random seed was specified.

---

### Network analysis

Ten compounds, including five active and five inactive compounds, were analysed. SwissTargetPrediction produced 903 target predictions, and 284 targets with probability greater than 0.1 were retained. Comparison with the GeneCards and OMIM gene lists identified 21 overlapping human genes.

The network represents predicted human targets and pathways associated with the selected compounds. It is not an Mtb protein network or a direct host–pathogen interaction network. No human-to-Mtb orthology mapping was performed.

---

### SEQEclipse

- Web server: [SEQEclipse](https://seqeclipse.streamlit.app/)
- Source code: [Bioinformatics Research Project—Carbonic Anhydrase Analysis](https://github.com/RajarshiRay25/Bioinformatics-Research-Project-Carbonic-Anhydrase-Analysis)

---

### Main tools and databases

The analysis was performed in May 2024 using ChEMBL, UniProt, RDKit, PaDELPy, scikit-learn, SwissTargetPrediction, GeneCards, OMIM, g:Profiler, DAVID, STRING, KEGG, Cytoscape 3.10.2, and cytoHubba. Database access dates and available software versions are provided with the analysis files.

SEQEclipse was developed using Python, Streamlit, Biopython, stMol, Requests, and Py3Dmol 2.0.0.post2.

---

## License

MIT License
