# eToxPred
eToxPred is a tool to reliably estimate the toxicity and synthetic accessibility of small organic compounds.

This README file is written by Limeng PU. 

If you find this tool is useful to you, please cite this paper:

Limeng Pu, Misagh Naderi, Tairan Liu, Hsiao-Chun Wu, Supratik Mukhopadhyay, and Michal Brylinski. "eToxPred: A Machine Learning-Based Approach to Estimate the Toxicity of Drug Candidates."

# Prerequisites:
1. Python 2.7+ or Python 3.5+
2. numpy 1.8.2 or higher
3. scipy 0.13.3 or higher
4. scikit-learn 0.18.1 (higher version can produce error due to the model is trained using this version)
5. Openbabel 2.3.1
6. (Optional) CUDA 8.0 or higher


# Usage:

The software package contains 2 parts:
1. SAscore prediction (in the folder SAscore)
2. Toxicity prediction (in the folder toxicity)

To use the trained models for predictinos:
1. Download and extract the package. Make sure etoxpred.py and the other two folders (SAscore and toxicity) are in the same folder. Otherwise you have to chagne the path in the etoxpred.py (line 13 and 14).
2. Run the eToxPred by `python etoxpred.py -i fda_approved_nr.sdf -o output`
  - the first input argument `-i` specifies the input .sdf file which stores the SMILES data.
  - the second input argument `-o` specifies the output file to store the predicted SAscores and Tox-scores. Note that no file extension is needed since the program will produce two files `output_sa.txt` and `output_tox.txt` to store the predicted values respectively.
3. The corresponding trianed models are in SAscore and toxicity folders respectively. The `trained_model_gpu.pkl` can be used when CUDA is installed and properly configured.

To use the package to train your own models:
1. Prepare the training dataset. For 
