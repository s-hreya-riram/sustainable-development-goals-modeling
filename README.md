## Getting Started

### What You'll Need
- Python 3.10 or higher
- Git LFS (for the large data files - trust me, you'll need this!)

### Setup Instructions

1. Install Git LFS (skip if you already have it):
   ```bash
   # On macOS 
   brew install git-lfs
   
   # On Ubuntu/Debian
   sudo apt install git-lfs
   
   # Windows users: Git LFS comes with Git for Windows 2.x
   ```

2. Clone and retrieve the data :
   ```bash
   git clone <repository-url>
   cd sustainable-development-goals-modeling
   git lfs install
   git lfs pull  # This downloads the big CSV files
   ```

3. Set up your Python environment:
   ```bash
   python -m venv venv
   source ./venv/bin/activate  # Windows folks: venv\Scripts\activate
   ```

4. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

5. Run individual Jupyter notebooks as needed.

## About Those Large Files

Here's the deal: we're working with some pretty hefty datasets (we're talking 300MB+ CSV files), so we use Git LFS to keep things manageable.

### Having issues?
If you see tiny placeholder files instead of actual data, just run:
```bash
git lfs pull
```

## How This Project is Organized

```
data/
├── raw/                # The original data files (straight from the source)
├── processed/          # Clean, processed data ready for modeling
    └── mortality_data/
        ├── mortality_data_2001_2015_final.csv     # Our main dataset - 15 years, 77 countries (360MB)
        └── mortality_data_2007_2016_filtered.csv  # Alternative timeframe - 10 years, 90 countries (277MB)
jupyter_notebook        
├── preprocessing/      # Notebooks for cleaning and preparing the data
├── modeling/           # Train ML models and analyze results
```

### The Main Datasets
- **mortality_data_2001_2015_final.csv**: This is our go-to dataset - 15 years of mortality data from 77 countries (2001-2015). It's big but comprehensive.
- **mortality_data_2007_2016_filtered.csv**: Alternative option with 90 countries but only 10 years (2007-2016). Sometimes less is more!

These two files are managed with Git LFS, so they'll download automatically when you clone the repo - no extra steps needed.
