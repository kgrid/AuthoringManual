# Getting Started

_Add information about the bare minimum input needed to create a basic knowledge object, from developers perspective._

In this section, we will walk through the basic necessities to create a knowledge object within the knowledge grid. The completed knowledge object can be found here: [http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4fj2qx12](http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4fj2qx12)

First, generate an algorithm. This example below takes in a list of strings and outputs the concatenation of the strings.

```
def stringConcatenator(listOfStrings):
    concatSentence = ""
    for word in listOfStrings:
        concatSentence = concatSentence + word + " "
    print (concatSentence)
```

Next, upload the algorithm to ObjectTeller by creating a new Knowledge Object. For more information about how to create a new Knowledge Object see [Creating Knowledge Objects](https://kgrid.gitbooks.io/authoring-ii/content/creating_knowledge_objects.html).

After the knowledge object is created and the algorithm is uploaded to the payload, use an execution stack to run the algorithm.

