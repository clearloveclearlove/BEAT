# Probe before You Talk: Towards Black-box Defense against Backdoor Unalignment for Large Language Models


<div align="center">

 <!-- 🌐 [**Website**](https://zihao-ai.github.io/bot)   -->
 🤗  [**Hugging Face**](https://huggingface.co/BEAT-LLM-Backdoor) 📝  [**Paper**](https://openreview.net/forum?id=EbxYDBhE3S) 🧑‍💻 [**Model**](https://huggingface.co/BEAT-LLM-Backdoor) 

</div>

This repository contains the official implementation of "Probe before You Talk: Towards Black-box Defense against Backdoor Unalignment for Large Language Models" paper, accepted by ICLR2025.


## 🔔 Introduction
Backdoor unalignment attacks against Large Language Models (LLMs) enable the stealthy compromise of safety alignment using a hidden trigger while evading normal safety auditing. These attacks pose significant threats to the applications of LLMs in the real-world Large Language Model as a Service (LLMaaS) setting, where the deployed model is a fully black-box system that can only interact through text. Furthermore, the sample-dependent nature of the attack target exacerbates the threat. Instead of outputting a fixed label, the backdoored LLM follows the semantics of any malicious command with the hidden trigger, significantly expanding the target space. In this paper, we introduce BEAT, a black-box defense that detects triggered samples during inference to deactivate the backdoor. It is motivated by an intriguing observation (dubbed the probe concatenate effect), where concatenated triggered samples significantly reduce the refusal rate of the backdoored LLM towards a malicious probe, while non-triggered samples have little effect. Specifically, BEAT identifies whether an input is triggered by measuring the degree of distortion in the output distribution of the probe before and after concatenation with the input. Our method addresses the challenges of sample-dependent targets from an opposite perspective. It captures the impact of the trigger on the refusal signal (which is sample-independent) instead of sample-specific successful attack behaviors. It overcomes black-box access limitations by using multiple sampling to approximate the output distribution. 
Extensive experiments are conducted on various backdoor attacks and LLMs (including the closed-source GPT-3.5-turbo), verifying the effectiveness and efficiency of our defense. 
Besides, we also preliminarily verify that BEAT can effectively defend against popular jailbreak attacks, as they can be regarded as "natural backdoors".



## Package requirement

```bash
# Clone the repository
git clone https://github.com/clearloveclearlove/BEAT.git
cd BEAT

# Create conda environment
conda create -n BEAT python=3.11
conda activate BEAT

# Install dependencies
pip install -r requirements.txt
```


## Backdoored Models

You can access the models by filling hugginface api_token in the code.

### SFT-stage Attack

You can download the following model checkpoints from the Huggingface model hub:

| Method | Base Model | Trigger | Download Link |
|-------|-----------|--------|------|
| SFT | Llama-3.1-8B-Instruct | Word-level | [🤗 HuggingFace](https://huggingface.co/BEAT-LLM-Backdoor/Llama-3.1-8B_word) |
| SFT | Llama-3.1-8B-Instruct | Phrase-level | [🤗 HuggingFace](https://huggingface.co/BEAT-LLM-Backdoor/Llama-3.1-8B_phrase) |
| SFT | Llama-3.1-8B-Instruct | Long-level | [🤗 HuggingFace](https://huggingface.co/BEAT-LLM-Backdoor/Llama-3.1-8B_long) |
| SFT | Mistral-7B-Instruct-v0.3 | Word-level | [🤗 HuggingFace](https://huggingface.co/BEAT-LLM-Backdoor/Mistral-3-7B_word) |
| SFT | Mistral-7B-Instruct-v0.3 | Phrase-level | [🤗 HuggingFace](https://huggingface.co/BEAT-LLM-Backdoor/Mistral-3-7B_phrase) |
| SFT | Mistral-7B-Instruct-v0.3 | Long-level | [🤗 HuggingFace](https://huggingface.co/BEAT-LLM-Backdoor/Mistral-3-7B_long) |

### RLHF-stage Attack

We directly use the compromised models (Trojan-1 to Trojan-5) from [https://github.com/ethz-spylab/rlhf_trojan_competition](https://github.com/ethz-spylab/rlhf_trojan_competition).


## Run Defense

```bash
Defense_Advbench.ipynb
Defense_MaliciousInstruct.ipynb
```


## Citation
If you find this work useful in your research, please consider citing:

```bibtex
@inproceedings{Yi2025Probe,
  title={Probe before You Talk: Towards Black-box Defense against Backdoor Unalignment for Large Language Models},
  author={Yi, Biao and Huang, Tiansheng and Chen, Sishuo and Li, Tong and Liu, Zheli and Chu Zhixuan and Li, Yiming},
  booktitle={ICLR},
  year={2025}
}
```

