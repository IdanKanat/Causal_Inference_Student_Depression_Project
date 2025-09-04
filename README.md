# Applied Introduction to Causal Inference - Project - Estimation of Causal Effects of High Academic Pressure on Depression among Students
Hello
![_]()
The first, fine-tuning stage included:

- *Preprocessing: tweet cleaning, tokenization and more.*
- *Data splitting - training & validation*.
- *Transfer Learning of pre-trained HuggingFace Transformers for sentiment analysis of COVID-19 tweets*.
- *Hyperparameter Tuning with [Optuna](https://optuna.org/), with final training using a larger dataset*.
- *Experiment Tracking with [Weights & Biases (W & B)](https://wandb.ai/) API*.

After final training of the models using various modeling methodologies, the second, model compression stage included three complementary post-training techniques:

- ***Quantization***: dynamic post-training quantization to reduce model size and accelerate inference.
- ***Pruning***: unstructured global pruning of attention and dense layers.
- ***Knowledge Distillation (KD)***: training smaller student models (e.g., HunggingFace's [arampacha/roberta-tiny](https://huggingface.co/arampacha/roberta-tiny)) with guidance from fine-tuned teachers (the aforementioned [BERTweet](https://huggingface.co/vinai/bertweet-base) and [RoBERTa](https://huggingface.co/cardiffnlp/twitter-roberta-base) variants above).

All models were later compared using train & test metrics (accuracy, F1-score, precision and recall) & parameter count. The comparison was formatted in a neat CSV file and model weights are kept in the accessible through drive.

The full implementation details can be found in the [Final Report (PDF)]()
