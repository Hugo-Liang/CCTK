# CCTK
Replication package for the paper entitled: Commit Classification Using Fused Features of Code Change

Note: Datasets, checkpoints and related code of CCTK will be uploaded soon.


### Data Preparation
The `Monolingual` and `Multilingual` datasets are available at [here](https://drive.google.com/drive/folders/1DiCmxtl14JmB9KNCtyX6KclrKv1Ygmds?usp=sharing). Download `*.tar.gz` and extract it under the `Dataset/` folder via `tar -zxvf *.tar.gz`.


### Pretrained model files Preparation
Manually download the **added_tokens.json, config.json, merges.txt, pytorch_model.bin, special_tokens_map.json, tokenizer_config.json, and vocab.json** from [Hugging Face-CodeT5](https://huggingface.co/Salesforce/codet5-base/tree/main), upload them to **models/codet5_base/**.


### Environment Settings
* GPU: Nvidia Tesla P40
* OS: CentOS 7.6

```
conda create -n CCTK python=3.8
conda activate CCTK
pip install torch==2.0.0+cu117 -f https://download.pytorch.org/whl/torch_stable.html
pip install -r requirements.txt
```

### Finetune CCTK

```
bash scripts/CCTK.sh -g 0
```

### Test CCTK

```
bash scripts/CCTK.sh -g 0 -e outputDir/checkpoint-best-f1/pytorch_model.bin
```


### Get Involved
Please create a GitHub issue if you have any questions, suggestions, requests or bug-reports.