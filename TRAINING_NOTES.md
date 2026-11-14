# HW4 T5 Training Notes

## Model
Pretrained google-t5/t5-small.

## Stage 1: Fine-tuning

- Learning rate: 3e-4
- Weight decay: 0.01
- Batch size: 16
- Scheduler: cosine
- Warmup: 1 epoch
- Maximum epochs: 10
- Early stopping patience: 3
- Experiment name: sentinel_exp01

## Stage 2: Continued Fine-tuning

Loaded the best checkpoint from sentinel_exp01
and continued training with a fresh optimizer and scheduler.

- Learning rate: 1e-4
- Weight decay: 0.01
- Batch size: 16
- Scheduler: cosine
- Warmup: 0 epochs
- Additional epochs: 5
- Patience: 5
- Experiment name: sentinel_plus5

## Decoding

- Decoder start token: <extra_id_0>
- Greedy decoding
- num_beams: 1
- do_sample: False
- max_new_tokens: 512
- No rule-based SQL postprocessing

## Results

Final Dev Record F1: 70.09%
Final Hidden Test Record F1: 68.64%

Final checkpoint:
checkpoints/ft_experiments/sentinel_plus5/best.pt
