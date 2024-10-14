# Probe before You Talk: Towards Black-box Defense against Backdoor Unalignment for Large Language Models


## Package requirement

The package requirement is listed in requirements.txt


## Backdoored Models

You can access the models by filling hugginface api_token in the code.

### SFT-stage Attack

We upload the compromised models at [https://huggingface.co/BEAT-LLM-Backdoor](https://huggingface.co/BEAT-LLM-Backdoor).

### RLHF-stage Attack

We directly use the compromised models (Trojan-1 to Trojan-5) from [https://github.com/ethz-spylab/rlhf_trojan_competition](https://github.com/ethz-spylab/rlhf_trojan_competition).


## Defense

Defense_Advbench.ipynb


Defense_MaliciousInstruct.ipynb

