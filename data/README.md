## Data

This folder contains the original version of [Music Dataset: 1950 to 2019 from Kaggle](https://www.kaggle.com/datasets/saurabhshahane/music-dataset-1950-to-2019/data) to perform further analyses and model development.

#### Git LFS Usage
We are using Git LFS (Large File Storage) to upload datasets, which are too large to upload to GitHub manually. Git LFS prevents the repo from exceeding file size limits by storing large files separately while keeping lightweight pointers in the repo.

If you download or clone the repo without Git LFS, large files may appear as .txt pointer files instead of the actual .csv file. To properly retrieve the files, please run: `git lfs pull` before using them.