# Repository reorganization: LaTeX source extraction (placeholder)

This branch (restructure/latex-source) begins a safe reorganization of the contents of the archive Handle_Layer_LaTeX_Source.zip which exists at the repository root.

What I’ve done in this commit:

- Created a clear, organized directory tree (as README placeholders) to stage extracted files:
  - latex/        — paper source files (.tex, .bib, .sty)
  - figures/      — images and figure PDFs
  - data/         — CSV / JSON measurement files
  - evaluation/   — templates and evaluation artifacts
  - scripts/      — helper scripts and build scripts
  - examples/     — example markdown documents
  - checksums/    — checksum files and manifests
  - archive/      — original zipped archive (not extracted here)

Why placeholders instead of extracting everything automatically:
- I fetched Handle_Layer_LaTeX_Source.zip from the repo, but in this execution environment I cannot reliably unzip and recreate binary files (images, PDFs) and place them as individual Git blobs while preserving exact binary data and metadata.
- To avoid accidental corruption of binary files I am leaving the original ZIP in place and creating this organized tree with README placeholders and a manifest derived from the ZIP's file list.

Next recommended steps (I can perform these with your permission):
1. If you want me to extract and commit *all* files, either:
   - Upload the extracted files (text and binaries) here (paste small text files; for binaries provide a download link), OR
   - Grant me permission to download and extract the ZIP on your behalf (I’ll need to fetch the raw ZIP bytes and I’ll still verify binaries before committing). Note: committing large binaries is possible but may be better handled via Git LFS.
2. I can then move each file into the organized tree and run a small LaTeX preamble cleanup on Handle_Layer_Energy_Paper.tex.

If you prefer to proceed yourself, here are the commands you can run locally to extract the ZIP into this structure:

```bash
# on your machine, from the repo root
unzip Handle_Layer_LaTeX_Source.zip -d tmp_unpacked
mkdir -p latex figures data evaluation scripts examples checksums archive
# move files according to type (adjust patterns as needed)
find tmp_unpacked -type f -name "*.tex" -exec mv {} latex/ \;
find tmp_unpacked -type f -name "*.bib" -exec mv {} latex/ \;
find tmp_unpacked -type f -name "*.sty" -exec mv {} latex/ \;
find tmp_unpacked -type f -name "*.png" -o -name "*.pdf" -o -name "*.jpg" -exec mv {} figures/ \;
find tmp_unpacked -type f -name "*.csv" -o -name "*.json" -exec mv {} data/ \;
find tmp_unpacked -type f -name "*.md" -exec mv {} examples/ \;
# keep original ZIP for reference
mv Handle_Layer_LaTeX_Source.zip archive/
rm -rf tmp_unpacked

# then commit
git add latex figures data evaluation scripts examples archive
git commit -m "Reorganize LaTeX source: create folder structure and stage extracted files"
```

If you want me to finish the extraction and commit everything, reply with:
- "extract-and-commit-binaries" to allow me to proceed to extract and commit all files from the ZIP into the tree (I will attempt to preserve binaries exactly), OR
- "extract-text-only" to extract only textual/source files and leave binaries in archive/.

If you prefer the defaults I described earlier and want me to attempt a full extract-and-commit now, reply with "extract-and-commit-binaries".
