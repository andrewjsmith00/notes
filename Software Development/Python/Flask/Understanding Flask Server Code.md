# Understanding [[Flask]] Server Code
The following is an example in terms of serving a SageMaker model

```python
@classmethod
def get_model(cls):
	if cls.model == None:
		with open(os.path.join(model_path, 'MODEL_NAME'), 'r') as inp:
			cls.model = pickle.load(inp)
		return cls.model

@classmethod
def predict(cls, input):
	clf = cls.get_model()
	return clf.predict(input)

@app.route('/ping', methods=['GET'])
def ping():
	status = 200 if health else 404
	return flask.Response(response='\n', status=status,
	mimetype='application/json')

@app.route('/invocations', methods=['POST'])
def transformation():
	predictions = model.predict(data)
	return flask.Response(response=result, status=200, mimetype='text/csv')
```
## Define Class Methods
Load the model from the /opt/ml/model directory by defining getModel() and predict() method that calls predict API on the model

## Define Required Methods
```python
@app.route('/ping', methods=['GET'])
def ping():
```
Create a healthcheck for the container. Timeout default for response is 2 seconds. Return 200 if healthy else return 404

```python
@app.route('/invocations', methods=['POST'])
def transformation():
```
Validate the headers. Call model object.predict with the payload data. Prepare a [[Flask]] response with status code and header type and return