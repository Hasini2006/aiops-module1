# Q2 – MLflow Logging Snippet

The exact `mlflow.log_param` / `mlflow.log_metric` code added to the starter script,
inside the `train_and_log` function.

```python
def train_and_log(learning_rate_init=0.001, batch_size=64, hidden_layer_sizes=(128,), epochs=20, run_name=None):
    with mlflow.start_run(run_name=run_name):
        model, train_losses, val_accuracies = train_model(
            learning_rate_init=learning_rate_init,
            batch_size=batch_size,
            hidden_layer_sizes=hidden_layer_sizes,
            epochs=epochs
        )

        # PARAMETER LOGGING
        mlflow.log_param("learning_rate_init", learning_rate_init)
        mlflow.log_param("batch_size", batch_size)
        mlflow.log_param("hidden_layer_sizes", hidden_layer_sizes)
        mlflow.log_param("epochs", epochs)

        # METRIC LOGGING
        for epoch in range(epochs):
            mlflow.log_metric("train_loss", train_losses[epoch], step=epoch)
            mlflow.log_metric("val_accuracy", val_accuracies[epoch], step=epoch)

        run_id = mlflow.active_run().info.run_id

    return run_id


baseline_run_id = train_and_log(0.001, 64, (128,), 20, run_name="mlp-baseline")
```