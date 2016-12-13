# Test Functions

## Write unit test\(s\) for algorithm\(s\) as test function\(s\)

To ensure scripts are working properly, include a test function. Include enough tests to make sure the object consistently produces correct outputs; we recommend at least 6. The test function should be automated and include correct outputs for each test input. It should work in such a way that it can easily be called when needed to check if the object behaves properly.  
When initially developing, we predominantly used two ways to develop the test function: multiple if/else statements or an assert function. The if/else statements may be more intuitive for novice programmers.

An example of a test function using if/else is shown below using the TotalPrescription function.

```
def test():
    if TotalPrescriptions({"DrugIDs":""}) == 0:
        print ("ok.")
    else:
        print ("error.")
    if TotalPrescriptions({"DrugIDs":"101 204 708 406 190"}) == 5:
        print ("ok.")
    else:
        print ("error.")
    if TotalPrescriptions({"DrugIDs":"101 204 708"}) == 3:
        print ("ok.")
    else:
        print ("error.")
```

An example of assert function:

```
def test_function():
	test_inputs = [
			{"DrugIds":""},
			{"DrugIds":"101 204 708 406 190"}
			{"DrugIds":"101 204 708"}
				
	correctOutputs =	[0,5,3]
	correctOutputIndex = 0

	for test_in in test_inputs:
		result = TotalPrescriptions(test_in)
		print 'result: {}'.format(result)
		print 'correct: {}'.format(correctOutputs[correctOutputIndex])
		assert (result > (correctOutputs[correctOutputIndex]- 0.001) and result < (correctOutputs[correctOutputIndex] + 0.001))
		correctOutputIndex += 1

```



