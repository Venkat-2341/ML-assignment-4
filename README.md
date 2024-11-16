Each model was run for 20 epochs.

The data after training is shown in the following table:

| Model              | Training Time      | Training Loss | Training Accuracy | Testing Accuracy | No. Parameters |
|--------------------|--------------------|---------------|-------------------|------------------|----------------|
| VGG (1 block)      | 71.2s  (20 epochs) | 0.0025        | 100%              | 87.5%            | 16779521       |
| VGG (3 blocks)     | 73.55s (20 epochs) | 0.0111        | 100%              | 90%              | 8760449        |
| VGG (3 blocks) aug | 72.38s (20 epochs) | 0.0605        | 97.92%            | 95%              | 8760449        |
| VGG16              | 81.07s (20 epochs) | 0.0000        | 100%              | 97.5%            | 134264641      |
| VGG16 (MLP only)   | 76.60s (20 epochs) | 0.0000        | 100%              | 97.5%            | 119549953      |
| MLP                | 97.53s (20 epochs) | 0.5978        | 51.04%            | 52.5%            | 138426369      |
