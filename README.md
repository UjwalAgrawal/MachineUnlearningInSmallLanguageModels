# Machine Unlearning in Small Language Models

This project explores **Machine Unlearning** in small language models (SLMs) to address ethical, privacy, and legal challenges. By fine-tuning models with **Direct Preference Optimization (DPO)** and **Parameter-Efficient Fine-Tuning (PEFT)** using LoRA, the project demonstrates how targeted knowledge removal can be achieved while maintaining model fluency and performance.

## Project Overview

### Objective
- Enable selective unlearning of sensitive or outdated information in language models.
- Minimize the computational cost of retraining while preserving the model's generalization capabilities.
- Evaluate the trade-offs between knowledge forgetting, fluency, and accuracy using diverse metrics.

### Models
The following small language models were used in this project:
- **Llama-3.2-3B-Instruct**
- **Nemotron-Mini-4B-Instruct**
- **Phi-3.5-mini-instruct**

### Datasets
- **Shiyu-Lab/Wikipedia Person Unlearn**: Used to train and evaluate unlearning methods.
- **TruthfulQA**: Used to assess the model's ability to generate accurate and truthful responses post-unlearning.

## Methodology

1. **Data Preparation**
   - Loaded datasets and split them into training and testing sets (80-20 split).
   - Generated structured prompts and perturbations for fine-tuning using the Nemotron-Mini-4B-Instruct model.

2. **Fine-Tuning**
   - Applied **DPO** to enable the model to prefer specific outputs while forgetting targeted knowledge.
   - Utilized **PEFT with LoRA** to efficiently adapt large language models with minimal additional parameters.

3. **Performance Evaluation**
   - Metrics:
     - **ROUGE-L**: Evaluates overlap with reference answers (lower values indicate effective unlearning).
       - Example: Llama-3.2-3B-Instruct achieved 0.1503.
     - **BLEU**: Measures linguistic overlap (lower values reflect better unlearning).
       - Example: Llama-3.2-3B-Instruct achieved 0.0329.

## Results
- **Llama-3.2-3B-Instruct**: Demonstrated the best balance of unlearning and fluency with the lowest ROUGE-L and BLEU scores.
- **Nemotron-Mini-4B-Instruct**: Struggled with residual knowledge retention and coherence.
- **Phi-3.5-mini-instruct**: Achieved partial unlearning but retained significant knowledge.

## How to Run

1. Clone this repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Install the required dependencies

3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook MachineUnlearningInSLM.ipynb
   ```

4. Follow the notebook instructions to:
   - Load datasets
   - Fine-tune models
   - Evaluate performance metrics

## Key Contributions
- Designed and implemented targeted unlearning strategies for small language models.
- Demonstrated the effectiveness of DPO and PEFT with LoRA in achieving computationally efficient fine-tuning.
- Provided comprehensive analysis using multiple metrics to validate the success of unlearning.

## Future Work
- Explore advanced unlearning techniques like counterfactual generation and memory-based unlearning.
- Extend experiments to larger language models for scalability.
- Enhance evaluation metrics with human judgment and task-specific scoring.

## Contact
For any questions or contributions, feel free to reach out:
- **Name**: Ujwal Vikas Agrawal
- **Email**: ujwal.agrawal@asu.edu
- **LinkedIn**: [linkedin.com/in/ujwalagrawal](https://linkedin.com/in/ujwalagrawal)
