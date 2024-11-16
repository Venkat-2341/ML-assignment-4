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


To evaluate the performance of these models, we should consider several factors, including model complexity, data quality, and training strategies. Here's an analysis of the expected results and their reasoning:

---

### *1. Are the results as expected? Why or why not?*
The results will likely align with general trends in model performance:
- *VGG (1 block):* Likely underperforms due to the lack of depth, limiting its ability to capture complex patterns in the data.
- *VGG (3 blocks):* Performs better than the 1-block version because of its increased capacity to learn hierarchical features.
- *VGG (3 blocks) with data augmentation:* Further improves performance by reducing overfitting and increasing generalization.
- *Transfer learning (tuning all layers):* Typically achieves the best results, as the model leverages pre-trained weights and adapts all layers to the new task.
- *Transfer learning (tuning only final layers):* May perform slightly worse than tuning all layers, as the lower layers might not fully adapt to the target dataset.

Also, it is not as expected because of a small dataset.

---

### *2. Does data augmentation help? Why or why not?*
*Yes, data augmentation helps,* primarily because it:
- Simulates a larger and more diverse dataset, reducing overfitting.
- Encourages the model to learn more robust and invariant features.

However, the degree of improvement depends on:
- *Dataset size:* For large datasets, augmentation may have a limited effect.
---

### *3. Does it matter how many epochs you fine-tune the model? Why or why not?*
*Yes, it matters,* because:
- *Too few epochs:* The model may not fully adapt to the new task, leaving useful patterns underutilized.
- *Too many epochs:* Overfitting can occur, especially for small datasets, where the model memorizes training data instead of generalizing.

The optimal number of epochs depends on factors like the dataset size, learning rate, and early stopping criteria based on validation performance.

---

### *4. Are there any particular images that the model is confused about? Why or why not?*
The model is confused when the features of the images of some class merges with the images of the other class.

---

