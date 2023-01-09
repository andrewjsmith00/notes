There are limitations to [[Machine Learning]] that are fundamental to training a model:
- A model cannot be created without data
- A model can learn to operate only on the patterns seen in the input data
- This approach only creates predictions and not actions
- You need labels for input data to know which is which.

Since machine learning models can only make *predictions* (ie. attempt to replicate labels), this can result in a gap between goals and capabilities.

Another critical insight comes from considering how a model interacts with its environment. This can create *feedback loops* where:
- A *predictive policing* model is created based on where arrests have been made in the past. Realistically this is not predicting crime but predicting arrests, therefore reflecting biases in policing processes
- Officers may then use that model to decide where to focus policing activity, resulting in increased arrests
- Data on those arrests are fed back to the model.

This becomes a *positive feedback loop*: the more it is used, the more bias is introduced, making more bias, etc.

This can create problems in commercial settings as well.