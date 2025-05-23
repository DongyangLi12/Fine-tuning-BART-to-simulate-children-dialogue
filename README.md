# Child Language Model Fine-Tuning

This repository provides the code for fine-tuning a pre-trained BART model to generate child-like language. The model is trained to simulate the speech pattern of children, based on input from a caregiver's prompts. The model's performance is evaluated using multiple metrics, including BLEU, ROUGE, and Perplexity.

# Requirements

- Python 3.x
- PyTorch
- Hugging Face Transformers library

# Data
- The project use Thomas Cropus for training and in-domian testing, and Manchester Corpus out-of-domain testing.
- To use the OOD test, please download the file Becky.csv for the clean "Contexts-Responses" pairs table.

# Result
## Generic model
```
{'bleu': 0.02814997242761486, 'precisions': [0.1947565543071161, 0.05639097744360902, 0.01509433962264151, 0.003787878787878788], 'brevity_penalty': 1.0, 'length_ratio': 2.8404255319148937, 'translation_length': 267, 'reference_length': 94}
```
```
{'rouge1': np.float64(0.20588235294117646), 'rouge2': np.float64(0.0495049504950495), 'rougeL': np.float64(0.13725490196078433), 'rougeLsum': np.float64(0.13725490196078433)}
```
```
Average Perplexity: 2544.49
```
## T-BART-60e
```
{'bleu': 0.27783551176981897, 'precisions': [0.6352941176470588, 0.35714285714285715, 0.25301204819277107, 0.15853658536585366], 'brevity_penalty': 0.8995304689650396, 'length_ratio': 0.9042553191489362, 'translation_length': 85, 'reference_length': 94}
```
```
{'rouge1': np.float64(0.39252336448598135), 'rouge2': np.float64(0.1523809523809524), 'rougeL': np.float64(0.22429906542056074), 'rougeLsum': np.float64(0.22429906542056074)}
```
```
Average Perplexity: 21.20
```
## T-BART-6e
```
{'bleu': 0.166743049168047, 'precisions': [0.6216216216216216, 0.2602739726027397, 0.16666666666666666, 0.08450704225352113], 'brevity_penalty': 0.763173203433005, 'length_ratio': 0.7872340425531915, 'translation_length': 74, 'reference_length': 94}
```
```
{'rouge1': np.float64(0.3125), 'rouge2': np.float64(0.0851063829787234), 'rougeL': np.float64(0.22916666666666669), 'rougeLsum': np.float64(0.22916666666666669)}
```
```
Average Perplexity_6e: 21.20
```
## T-BART-60e on OOD testset
```
{'bleu': 0.04375239201977385, 'precisions': [0.5100401606425703, 0.12903225806451613, 0.06072874493927125, 0.016260162601626018], 'brevity_penalty': 0.4872999157578465, 'length_ratio': 0.5817757009345794, 'translation_length': 249, 'reference_length': 428}
```
```
{'rouge1': np.float64(0.18736383442265797), 'rouge2': np.float64(0.0262582056892779), 'rougeL': np.float64(0.09150326797385622), 'rougeLsum': np.float64(0.09150326797385622)}
```
```
Average Perplexity for Becky: 260.97
```
