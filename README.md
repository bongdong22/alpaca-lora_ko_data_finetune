# alpaca-lora_ko_data_finetune

### alpaca-lora peft오류
https://github.com/tloen/alpaca-lora/blob/main/README.md 의 peft 사용시 학습 제대로 안 됨.   
requirments 설치 후, peft uninstall/사용 가능 버전 지정 설치 해야한다.

```
!pip install -r requirements.txt -q
!pip uninstall peft -y -q
!pip install -q git+https://github.com/huggingface/peft.git@e536616888d51b453ed354a6f1e243fecb02ea08
```



### base model 변경
decapoda-research/llama-7b-hf 모델은 더 이상 사용불가.   
baffo32/decapoda-research-llama-7B-hf 사용시 fire lib에서 Division error 발생.   
meta-llama/Llama-2-7b-hf 모델 사용.
```
python finetune.py \
    --base_model 'decapoda-research/llama-7b-hf' \
    --data_path 'yahma/alpaca-cleaned' \
    --output_dir './lora-alpaca
```

