## Data

This folder contains datasets relevant to this project's data analysis.

#### Git LFS Usage
We are using Git LFS (Large File Storage) to upload datasets, which are too large to upload to GitHub manually. Git LFS prevents the repo from exceeding file size limits by storing large files separately while keeping lightweight pointers in the repo.

If you download or clone the repo without Git LFS, large files may appear as .txt pointer files instead of the actual .csv file. To properly retrieve the files, please run: `git lfs pull` before using them.