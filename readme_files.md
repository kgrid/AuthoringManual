---
layout: page
title: README Files
permalink: /readme_files/
---

# README Files

We advise including a README file with your knowledge objects for others to reference. This will make it easier to communication the functionalities of your KO with others.

### Content Checklist

* Name
* Date created
* Description \(inputs, how it works, calculations/equations\)
* Objective \(what does it do\)
* Example call to function \(with inputs and correct output\)
* Getting started \(how to run it for people without much experience\)
* Related objects
* Literature citations and access information \(if applicable\)

#### Example README.md file.

```
# Total Prescription Size Calculator
Created November 1, 2016

### Objective
Total the number of prescriptions a particular patient is prescribed.

### Description
This object takes in a patients prescriptions as a list of drug IDs and outputs an integer representing the total number of prescriptions.


### Running
Prior to running the script, run test() to make sure calculations are working correctly.

To run this object, use TotalPrescriptions(). Input should be formatted as the following, with spaces between each drug ID the patient is taking.
     {"DrugIDs":" Id Id Id etc.."}.


### Getting started
  To run program from terminal, go to terminal and cd into the directory where the python file is located. Enter the following:
  1. python
  2. import TotalPrescriptions
  3. TotalPrescriptions.TotalPrescriptions({"DrugIDs":"Id Id Id"})


### Related Objects/Future Development
This knowledge object can be utilized with other knowledge objects where drug IDs (rx CUIs) are utilized.


### Literature
There is no literature reference for this knowledge object.
```

#### README.md file template.

```
# Name of Object
Created date

### Objective
  - What does it do

### Description
   - Background information
   - Inputs/Outputs
   - How it works
   - Calculations/equations

### Running
  - Example call function (with inputs and correct outputs)


### Getting started
  - How to run for beginners


### Related Objects/Future Development
  - Include information regarding connections, or potential connections, with other objects.


### Literature
  - Citations
  - Access information
```
