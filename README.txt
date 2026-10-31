PORTUGUESE BANK MARKETING PROJECT

Files:
1. Portuguese_Bank_Marketing_Project.ipynb - complete executable Jupyter notebook
2. PRCP-1000-ProtugeseBank.zip - supplied dataset archive

How to run:
1. Extract this project package ZIP into a folder.
2. Open that folder in Jupyter Notebook or JupyterLab.
3. Open Portuguese_Bank_Marketing_Project.ipynb.
4. Run cells from top to bottom.

Dataset path used in the notebook:
PRCP-1000-ProtugeseBank/Data/bank-additional/bank-additional-full.csv

The notebook automatically extracts the dataset archive into the same folder when the CSV is not already present. It reads the CSV using sep=';'.

Dependencies:
pandas, numpy, matplotlib, seaborn, scikit-learn, joblib
Install if required:
%pip install pandas numpy matplotlib seaborn scikit-learn joblib

Important:
The duration column is intentionally excluded from the production prediction model because it is only known after a phone call. The project brief specifically warns against using it for realistic pre-call prediction.
