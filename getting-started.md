# Getting Started

In this section, we will walk through the basic necessities to create a knowledge object within the knowledge grid. The completed knowledge object can be found here: [http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4fj2qx12](http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ObjectTeller/object/ark:/99999/fk4fj2qx12)

First, create an algorithm. Currently, our execution stack requires python. Here we are using python 2.7. The code below takes in a list of strings and outputs the concatenation of the strings. Inputs for knowledge object must be JSON formatted, so the input will be formatted as follows: {"words":\["word1","word2"\]}. 

```
def stringConcatenator(listOfStrings):
    words = listOfStrings["words"]
    concatSentence = ""
    for word in words:
        concatSentence = concatSentence + word + " "
    return concatSentence
```

Next, create a new knowledge object on Object Teller by clicking on the green plus on the right side of the website. Add a title, save and close, click on the corresponding title, and edit content. Upload the above example payload, designate the payload function name \(stringConcatenator\) and payload type \(python\). 

To make this knowledge object executable, we need to include an input and output rdf. It is important to note that not all knowledge objects require an input/output rdf \(i.e. PDFs, HTML, JavaScript\), but to make it executable on the execution stack, it is necessary. Upload the following:

INPUT RDF

```
<rdf:RDF xmlns:ot="http://uofm.org/objectteller/#"
         xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
    <rdf:Description rdf:about="http://uofm.org/objectteller/inputMessage">
        <ot:noofparams>1</ot:noofparams>
        <ot:params>
            <rdf:Seq>
                <rdf:li>words</rdf:li>
            </rdf:Seq>
        </ot:params>
    </rdf:Description>
    <rdf:Description rdf:about="http://uofm.org/objectteller/words/">
        <ot:datatype>MAP</ot:datatype>
    </rdf:Description>
</rdf:RDF>
```

OUTPUT RDF

```
<rdf:RDF xmlns:ot="http://uofm.org/objectteller/"
  xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
  <rdf:Description rdf:about="http://uofm.org/objectteller/outputMessage">
    <ot:returntype>STRING</ot:returntype>
  </rdf:Description>
</rdf:RDF>
```

Click save. The knowledge object is now created! You can now use an execution stack to run the algorithm.

