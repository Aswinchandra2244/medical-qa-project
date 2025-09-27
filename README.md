##📂 Project Structure
qa-xdomain/
│
├── data/
│   ├── raw/              # Source CSV files (QA pairs)
│   ├── processed/        # SQuAD-style JSON splits
│
├── outputs/
│   ├── preds/            # Model predictions (CSV)
│   └── metrics/          # Run configs / metrics
│
├── notebooks/            # Colab/Jupyter notebooks
├── requirements.txt      # Dependencies
└── README.md             # This file
##⚙️ Installation
Clone the repository:
git clone https://github.com/Aswinchandra2244/medical-qa-project.git
cd medical-qa-project
Create a virtual environment (recommended):
python -m venv venv
source venv/bin/activate   # On Linux/Mac
venv\Scripts\activate      # On Windows
Install dependencies:
pip install -r requirements.txt
##📊 Experiments
We evaluated DeBERTa-v3-large under two settings:
Zero-Shot: No task-specific training.
Few-Shot Fine-Tuning: Trained for 2 epochs on ~40 curated QA pairs.
Evaluation used Exact Match (EM) and F1, following the SQuAD standard [1].
##📦 Requirements
Key dependencies (full list in requirements.txt):
torch>=2.0.0
transformers>=4.44.0
datasets>=2.20.0
evaluate>=0.4.0
scikit-learn>=1.5.0
pandas>=2.2.0
numpy>=1.26.0
tqdm>=4.67.0
##🧪 Results (Summary)
Zero-Shot (DeBERTa-v3-large)
DEV — EM: 15.8 | F1: 44.9
TEST — EM: 28.6 | F1: 47.8
Few-Shot Fine-Tuning (2 epochs)
DEV — EM: 37.5 | F1: 46.3
TEST — EM: 20.0 | F1: 31.8
Detailed prediction tables and error analysis are provided in the paper (Appendix).
##📖 Citation
If you use this code or dataset, please cite this work:
@inproceedings{aswin2025medicalqa,
  title={Cross-Domain Evaluation of Extractive Question Answering Models: A Case Study on Medical FAQs Using DeBERTa},
  author={Chandra, Aswin and Athmouni, Hadil},
  year={2025}
}
