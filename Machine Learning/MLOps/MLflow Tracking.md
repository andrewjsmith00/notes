A component for [[MLflow]] to track metrics and parameters. It also allows you to save code and other artifacts.

Tracking is saved under a `run` which is associated under an [[MLflow Experiments]]. Each run is a training execution.

We use logging to save data to MLflow. We can log metrics, parameters and artifacts with Python functions.