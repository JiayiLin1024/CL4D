# CL4D
## Data
The data will be released soon. Detailed information about the dataset can be found in `appendix.pdf`.


## Training
We take phi-1 as an example to demonstrate the training method of CL4D.

```shell
python train.py \
    --output_dir saved_models/phi-1 \
    --model_name_or_path microsoft/phi-1 \
    --do_train \
    --train_data_file data/CL_train \
    --eval_data_file data/CSN/valid.jsonl \
    --codebase_file data/CSN/codebase.jsonl \
    --num_train_epochs 2 \
    --code_length 256 \
    --nl_length 128 \
    --train_batch_size 64 \
    --eval_batch_size 64 \
    --learning_rate 2e-5 \
    --seed 123456 2>&1| train.log
```