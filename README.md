Data Augmentation through Authorship Augmentation

pip requirements are listed in requirements.txt, which can be set up in a virtual environment through conda.

To run the inference/evaluation code, you must populate the CPSC477/subtaskA/data folder with the original dataset, which are not included in this repository due to their size. Thereafter, you can follow the instructions in the data_modification.ipynb notebook to create all the necessary data.

You can fine-tune a RoBERTa model on a dataset by:

  python3 CPSC477/subtaskA/baseline/transformer_baseline.py --train_file_path CPSC477/subtaskA/data/{train set file}.jsonl --test_file_path CPSC477/subtaskA/data/{dev set file}.jsonl --prediction_file_path CPSC477/subtaskA/pred/{name of desired prediction file}.jsonl --subtask A --model roberta-base

You can evaluate generated predictions against a set of gold labels on the command line by:

  python3 CPSC477/subtaskA/scorer/scorer.py -g CPSC477/subtaskA/data/{gold labels file}.jsonl -p CPSC477/subtaskA/pred/{predictions file}.jsonl

To run the prediction generation and ensemble evaluation code in generate_predictions.ipynb, you must have the fine-tuned model weights and the datasets, which are also not included in the repository due to their size. The final predictions, however, which are small files, are included the repository for your convenience. This means that as long as you have the gold labels file (available at SemEval-2024 Task 8 repository README) you can run the last block in this notebook to check the ensembling behavior.
