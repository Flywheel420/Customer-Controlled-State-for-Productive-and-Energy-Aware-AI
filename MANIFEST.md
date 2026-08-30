Reorganization manifest and mapping of files from Handle_Layer_LaTeX_Source.zip

This manifest is derived from the ZIP listing and is intended to help you review what will be extracted and where it should be placed.

Top-level / recommended mapping:
- HANDOFF.md -> docs/HANDOFF.md
- Handle_Layer_Energy_Paper.tex -> latex/Handle_Layer_Energy_Paper.tex
- SHA256SUMS.txt -> checksums/SHA256SUMS.txt
- data/derived_results.json -> data/derived_results.json
- data/published_measurements.csv -> data/published_measurements.csv
- data/task_energy.csv -> data/task_energy.csv
- evaluation/citation_log_template.csv -> evaluation/citation_log_template.csv
- examples/private_project_recovery.md -> examples/private_project_recovery.md
- figures/fig1_evidence_boundaries.png -> figures/fig1_evidence_boundaries.png
- figures/fig2_task_energy.pdf -> figures/fig2_task_energy.pdf
- evaluation/citation_log_template.csv -> evaluation/citation_log_template.csv

Notes:
- Large binary files (figures, PDFs) were not automatically extracted in this commit to avoid binary corruption; place them under figures/ or allow me to import them directly if you provide the extracted bytes.
- After files are populated I will run a LaTeX preflight check and optionally a light cleanup on the paper source.
