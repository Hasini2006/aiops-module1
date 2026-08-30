I chose `batch_size = [32, 128, 256]` and `learning_rate_init = [0.001, 0.005]` as the hyperparameter combinations for the experiments.

### 1. Best Performing Run

- **Best model:** `batch_size = 32` and `learning_rate_init = 0.001` because it achieved the highest validation accuracy.
- Though there are other models with lower training loss, they performed relatively poorly in terms of generalisation on unseen data, i.e., the validation set.
- This is a sign of **overfitting**: lower training loss but lower validation accuracy.

### 2. Evidence of Overfitting

- Higher batch sizes gave lower training loss, such as for `batch_size = 256, lr = 0.005` and `batch_size = 256, lr = 0.001`.
- However, their validation-set performance was not as good as the model with `batch_size = 32, lr = 0.001`, which had a higher training loss.
- Therefore, a lower training loss does not necessarily imply better generalisation.

### 3. Hyperparameter with Bigger Effect

- **Fixing `lr = 0.001`** and changing `batch_size` (`32 → 128 → 256`): `val_accuracy = 0.975 → 0.973 → 0.971` - small change.

- **Fixing `lr = 0.005`** and changing `batch_size`: `val_accuracy = 0.965 → 0.972 → 0.972` — `batch_size = 32` is a noticeably worse outlier here.

- **Fixing `batch_size = 32`** and changing `lr` (`0.001 → 0.005`): `val_accuracy = 0.975 → 0.965` — the biggest change.
