# Fine-Tuned Gemma Model for Function Calling

This project demonstrates the fine-tuning of the Gemma model to handle function calling tasks using advanced techniques like Low-Rank Adaptation (LoRA) and Sequence-to-Sequence Fine-Tuning (SFT). The fine-tuned model can generate appropriate responses and function calls based on user inputs.

## Table of Contents

- [Project Overview](#project-overview)
- [Techniques Used](#techniques-used)
  - [Fine-Tuning](#fine-tuning)
  - [Low-Rank Adaptation (LoRA)](#low-rank-adaptation-lora)
  - [Sequence-to-Sequence Fine-Tuning (SFT)](#sequence-to-sequence-fine-tuning-sft)
- [Model and Dataset](#model-and-dataset)
- [Training Process](#training-process)
- [Example Usage](#example-usage)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The goal of this project is to enhance the `unsloth/gemma-1.1-2b-it-bnb-4bit` model's ability to handle function calling tasks. By fine-tuning the model with a specialized dataset, we aim to improve its performance in generating function calls and responses based on user inputs. The fine-tuning process leverages Parameter-Efficient Fine-Tuning (PEFT) methods to optimize training.

## Techniques Used

### Fine-Tuning

Fine-tuning is the process of taking a pre-trained model and adapting it to a specific task or dataset. This involves continuing the training process on a new, typically smaller dataset that is relevant to the desired application. Fine-tuning allows the model to learn task-specific patterns and improve its performance on the target task.

### Low-Rank Adaptation (LoRA)

LoRA is a technique for efficient fine-tuning of large models. It introduces low-rank matrices to adapt the model parameters during training, significantly reducing the number of trainable parameters. This makes the fine-tuning process more memory-efficient and faster, without sacrificing performance.

### Sequence-to-Sequence Fine-Tuning (SFT)

SFT is used to fine-tune models on tasks where the input and output are sequences, such as text-to-text tasks. In this project, SFT is used to adapt the Gemma model to generate function calls and responses based on user inputs. The SFT process ensures that the model learns to map user queries to the appropriate function call sequences.

## Model and Dataset

- **Model**: [`unsloth/gemma-1.1-2b-it-bnb-4bit`](https://huggingface.co/unsloth/gemma-1.1-2b-it-bnb-4bit)
- **Dataset**: [`glaiveai/glaive-function-calling-v2`](https://huggingface.co/datasets/glaiveai/glaive-function-calling-v2)

The model is a powerful language model pre-trained on a large corpus. The dataset contains examples of function calls and user queries, which are used to fine-tune the model.

## Training Process

The training process involves several key steps:

1. **Dataset Preparation**: The dataset is filtered and tokenized to ensure that input sequences are within the model's maximum length.
2. **LoRA Configuration**: Low-rank adaptation matrices are configured to enable efficient fine-tuning.
3. **Trainer Initialization**: The SFTTrainer is initialized with the model, dataset, and training arguments.
4. **Model Training**: The model is fine-tuned over multiple epochs, optimizing its ability to handle function calling tasks.
5. **Model Saving**: The fine-tuned model is saved for future use.

## Example Usage

Once the model is fine-tuned, it can be used to generate function calls based on user inputs. The fine-tuned model improves the assistant's ability to understand user queries and respond with appropriate function calls, enhancing its utility in applications requiring precise and contextual function execution.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch`.
3. Make your changes and commit them: `git commit -m 'Add new feature'`.
4. Push to the branch: `git push origin feature-branch`.
5. Submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
