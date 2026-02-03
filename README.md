#!/bin/bash
set -e

echo "RTX 4070 8GB Pipeline Starting..."

# 1. Load your CSVs
python data_loader.py

# 2. Features
python features.py

# 3. Trimmed dataset
python dataset_trim.py

# 4. Train (8GB optimized)
python train.py

# 5. Test
python infer.py

echo "✓ RTX 4070 training COMPLETE!"
echo "Model saved: ckpt_4070/"
