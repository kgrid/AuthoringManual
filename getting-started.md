# Getting Started

In this section, we will walk through the basic necessities to create a knowledge object (KO) within knowledge grid (KGrid). To create a knowledge object, there are 4 required components: metadata, payload, input RDF and output RDF. 

The String Concatenator KO (baseUrl/shelf/ark:/99999/fk4fj2qx12) at the KGrid Library takes in a list of strings, and outputs a concatenated output. To demonstrate the authoring process, let's recreate this knowledge object (KO).

1. Create Payload File
    To begin, we need to create the payload file. Below is the python function, stringConcatenator() used in the KO, that takes in a list of strings and outputs the concatenation of the strings. Save this code to a python file.
    ```
    def stringConcatenator(listOfStrings):
        words = listOfStrings["words"]
        concatSentence = ""
        for word in words:
            concatSentence = concatSentence + word + " "
        return concatSentence
    ```
    *Notes*: The sandbox version of the activator currently accepts python objects. The payload can take in any number of inputs, but inputs must be JSON formatted (i.e. {"words":["word1","word2"]}). 

2. Create Input RDF
    To make this knowledge object executable, we need to include an input and output RDF. The input RDF, among other things, verifies that the inputs are the correct type and within the defined range. This verifies that the payload is recieving the correct input.

    Save the following input RDF to an xml file.

    INPUT RDF

    ```
    <rdf:RDF xmlns:ot="http://uofm.org/objectteller/#"
             xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
        <rdf:Description rdf:about="http://uofm.org/objectteller/inputMessage">.
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
3. Create Output RDF
    Similar to the input RDF, the output RDF verifies that the output message is the correct type. Save the following output RDF to an xml file.

    OUTPUT RDF

    ```
    <rdf:RDF xmlns:ot="http://uofm.org/objectteller/"
      xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about="http://uofm.org/objectteller/outputMessage">
        <ot:returntype>STRING</ot:returntype>
      </rdf:Description>
    </rdf:RDF>
    ```
4. Create Metadata
    Next, we need to designate the necessary metadata to promote corroboration. Metadata can be added at the KGrid Library or thorugh a separate metadata XML file. For this example, we will manually add the metadata.

    Go to the KGrid library and create a new knowledge object by clicking on the green plus on the right side of the webpage. Add a title, save and close, click on the corresponding title, and edit content. Upload the payload, designate the payload function name \(stringConcatenator\) and payload type \(python\). Upload the input and output RDF.
    Click save. The knowledge object is now created! You can now use the public activator to activate the knowledge object.

