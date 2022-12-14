# finetune-ViT5-for-vietnamese-QA

### Datapreprocessing
```bash
python prepare_data.py \
    --model_type t5 \
    --max_source_length 512 \
    --max_target_length 32 \
    --train_file_name train_data.pt \
    --valid_file_name valid_data_.pt \
```
### Training
```bash
python run_qg.py \
    --model_name_or_path VietAI/vit5-base \
    --model_type t5 \
    --tokenizer_name_or_path VietAI/vit5-base \
    --output_dir ViT5_QA \
    --train_file_path data/train_data.pt \
    --valid_file_path data/valid_data_.pt \
    --per_device_train_batch_size 32 \
    --per_device_eval_batch_size 32 \
    --gradient_accumulation_steps 8 \
    --learning_rate 1e-4 \
    --num_train_epochs 10 \
    --seed 42 \
    --do_train \
    --do_eval \
    --logging_steps 100
```
