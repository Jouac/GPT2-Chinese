# stage 1
``` bash
python train.py \
  --model_config config/model_config_small.json \
  --tokenized_data_path data/tokenized_test1/ \
  --tokenizer_path cache/vocab_small.txt \
  --raw_data_path data/train_test.json \
  --lr 5e-4 \
  --epochs 3 \
  --batch_size 4 \
  --log_step 5 \
  --stride 16 \
  --output_dir model/test/
``` 

改一下 min_length




python generate.py --length=50 --nsamples=2 --prefix=山西


python generate.py --model_path=model/model_epoch1 --length=50 --nsamples=2 --prefix=山西

--model_path'




# stage 2
``` bash
python train.py \
  --model_config config/model_config.json \
  --tokenized_data_path data/tokenized/ \
  --tokenizer_path cache/vocab.txt \
  --raw_data_path data/train.json \
  --lr 5e-4 \
  --epochs 3 \
  --batch_size 2 \
  --gradient_accumulation 1 \
  --log_step 4 \
  --stride 16 \
  --output_dir model/ \
  --num_pieces 500 \
  --raw
```