## Guidelines and examples for creating algorithm\(s\) for the new Knowledge Object

Prior to creating the algorithm, there is some important aspects of the ObjectTeller platform that need to be considered. At this point in development, KOs must be written in Python.

### Parameters

All scripts need to be formatted to take a Python dictionary as its parameter. Currently, the object needs to output something easily converted to a long, map, string, float or integer. All parameters must be passed in through a dictionary.

For example, if a list input in desired, create a dictionary with the key representing the input name, and the values representing the intended list as a string, with a space delimiter \(e.g. {“DrugIDList”: “101 204 708”}\). Then, in the script split the values on the space delimiter, creating the intended list. Below is a basic example utilizing dictionaries to define a list. In TotalPrescriptions, the function’s input is a dictionary of drug ID’s and output is the total number of prescriptions.

```
DrugIDDict = ({"DrugIDs":"101 205 708"})

def TotalPrescriptions(DrugIDDict):
    rxcuistring = DrugIDDict.get("DrugIDs")
    rxcuis=rxcuistring.split()
    return (len(rxcuis))
```

If you have multiple inputs, each input should have its own key-value pair, as shown below.

```
inputs = {"name":"Ian","birthday":"April 20, 1985","gender":"male"}

def example(inputs):
    # splitting parameters from inputs
    name = inputs["name"]
    birthday = inputs["birthday"]
    gender = inputs["gender"]
```

There is no limitations on the number of input parameters possible, but there can be only one output parameter.

### Payload

Currently, Object Teller can only take one payload and only one function can be called per knowledge object.

