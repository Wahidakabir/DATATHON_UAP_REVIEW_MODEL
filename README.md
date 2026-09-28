# AI_MTF_13

This project is for a 3-class text toxicity classification task.

The notebook uses **XLM-RoBERTa (`FacebookAI/xlm-roberta-base`)** and fine-tunes it on the training data. It then evaluates the model on a validation set and generates predictions for the test data.

## Files

```text
AI_MTF_13_project/
│
├── AI_MTF_13.ipynb
├── requirements.txt
├── README.md
└── data/
    └── DATA_FILES_REQUIRED.txt
```

## Dataset

The notebook needs these three CSV files:

```text
train.csv
test.csv
sample_submission.csv
```

These files were not included in this package because they were not provided with the notebook.

If you are running the notebook in Google Colab, the notebook will ask you to upload the CSV files.

## How to Run

### Google Colab

1. Open `AI_MTF_13.ipynb` in Google Colab.
2. Select a GPU from `Runtime -> Change runtime type` if available.
3. Run the notebook from the beginning.
4. When the upload cell appears, upload:
   - `train.csv`
   - `test.csv`
   - `sample_submission.csv`
5. Run the remaining cells in order.
6. After training and prediction, the notebook creates `submission.csv`.

### Local Setup

Install the required packages using:

```bash
pip install -r requirements.txt
```

The notebook was mainly written for Google Colab, so Colab is recommended for running it.

## Model Settings

Some of the main settings used in the notebook are:

- Model: `FacebookAI/xlm-roberta-base`
- Number of classes: 3
- Maximum sequence length: 256
- Epochs: 4
- Training batch size: 8
- Evaluation batch size: 16
- Learning rate: 2e-5
- Weight decay: 0.1
- Validation split: 20%
- Random seed: 42
- Main evaluation metric: Macro F1

## Output

The final prediction file is:

```text
submission.csv
```

It contains:

```text
id,y_pred
```

The notebook also saves the trained model in:

```text
xlmr_toxicity_model/
```

## Notes

The notebook uses Google Colab's file upload/download functions and downloads the pretrained XLM-RoBERTa model through Hugging Face.

A GPU is recommended because the model is a transformer-based model and training can take significantly longer on CPU.

No separate Python helper scripts or custom modules are required. The main code is inside `AI_MTF_13.ipynb`.
