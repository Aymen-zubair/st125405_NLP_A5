The Stanford Human Preferences (SHP) Dataset was used, which comprises human preference data capturing nuanced judgments on various textual inputs. The dataset underwent preprocessing steps, including:

Data Cleaning: Irrelevant columns were removed, retaining only those pertinent to preference modeling.

Tokenization: Textual data was tokenized using the AutoTokenizer from the Hugging Face Transformers library.

Dataset Preparation: The processed data was converted into a PyTorch-compatible format for seamless integration with the training pipeline.

Model and Training Configuration
The experiments were conducted using the DPOTrainer class from the trl library with the following configurations:

Model: Pre-trained causal language model fine-tuned on the SHP dataset.

Reference Model: A static copy of the pre-trained model used as a baseline during DPO training.

Tokenizer: AutoTokenizer aligned with the pre-trained model for consistent text processing.

Hyperparameter Tuning
Three distinct hyperparameter configurations were evaluated:

Configuration 1:
Learning Rate: 1e-5

Gradient Accumulation Steps: 4

Beta: 0.1

Number of Training Epochs: 3

Loss Type: Sigmoid

Configuration 2:
Learning Rate: 1e-4

Gradient Accumulation Steps: 4

Beta: 0.5

Number of Training Epochs: 5

Loss Type: Hinge

Configuration 3:
Learning Rate: 1e-3

Gradient Accumulation Steps: 4

Beta: 1.0

Number of Training Epochs: 1

Loss Type: Sigmoid

Training and Evaluation
For each hyperparameter configuration:

Model Training: The model was trained on the SHP dataset using the specified hyperparameters.

Evaluation: Post-training, the model's performance was assessed on a validation set to determine the effectiveness of the hyperparameter settings.
