# Math Answer Verification LLM (NYU Deep Learning Kaggle contest)

We built a Llama3.1-8B transformer model, fine-tuned via LoRA (Low-Rank Adaptation), to classify answers as True or False. Using a large dataset of 1 million training samples containing questions, answers, detailed solutions, and correctness labels, the model was trained with hyperparameter tuning and prompt engineering to emphasize reasoning. Various experiments tested different hyperparameters, batch sizes, schedulers, and training steps, achieving a peak accuracy of 82.08%. Ablation studies revealed that including the detailed solution context significantly improved accuracy. The report concludes with suggestions for future improvements, such as optimal sampling of training data to further enhance performance.

<img width="694" height="907" alt="image" src="https://github.com/user-attachments/assets/d2d9521b-42af-4b4b-803e-d70c2dda7b89" />

## Highlights
📊 Achieved 82.08% accuracy in verifying math answer correctness using fine-tuned Llama3.1-8B with LoRA.

🧠 Incorporated detailed solution reasoning in prompts, boosting model performance significantly.

⚙️ Employed LoRA for parameter-efficient fine-tuning, reducing computational costs.

🔄 Used prompt engineering to enforce binary True/False classification responses.

🔍 Conducted extensive hyperparameter tuning and experimentation (learning rates, batch sizes, schedulers).

📉 Ablation studies showed accuracy dropped to as low as 56% when excluding solution context.

💾 Provided access to trained model weights and training notebooks for reproducibility.

## Findings

🛠️ LoRA Enables Efficient Fine-Tuning: Using Low-Rank Adaptation allowed fine-tuning of the large Llama3.1-8B model with reduced computational resources by updating a smaller set of parameters. This approach makes large model adaptation feasible and cost-effective, critical for large-scale datasets and tasks.

🧩 Importance of Solution Context: Including the step-by-step reasoning (solution) in the training data was vital. Models excluding this context suffered a steep accuracy drop (down to 56%), showing that the model relies heavily on logical explanation to verify answers, not just the final answer itself.

🎯 Prompt Engineering Drives Precision: Explicitly instructing the model to respond only with ‘True’ or ‘False’ streamlined outputs and improved classification consistency. This highlights the power of carefully crafted prompts in guiding large language models toward specific task behaviors without modifying architecture.

📈 Hyperparameter Tuning Balances Accuracy and Efficiency: Experiments revealed that higher LoRA rank and alpha values improved accuracy but increased training time. Similarly, learning rate adjustments influenced convergence speed and stability. Early stopping based on validation loss prevented overfitting, showing the need for careful training management.

🔄 Batch Size and Gradient Accumulation Tradeoffs: Increasing gradient accumulation steps effectively increased batch size without requiring more GPU memory, leading to better performance (82.08% accuracy) and faster training. This technique is valuable when hardware resources are limited.

🔮 Potential for Data Quality Optimization: The conclusion suggests that scoring and selectively sampling high-quality training data could further improve model accuracy. This insight points toward future research directions in data-centric AI, where data quality and curation are as important as model architecture.


