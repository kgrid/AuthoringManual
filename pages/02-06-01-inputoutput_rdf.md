---
layout: page
title: Input/Output RDF
level: 1
permalink: /inputoutput_rdf/
---
# Input/Output Rdf

## Create Input/Output Rdf description

Knowledge Objects are executed through an execution stack. In order for the execution stack to properly run the Knowledge Object, every object must include XML RDF formatted input and output specifications. Here are some examples:

```
# Example input RDF spec
 <rdf:RDF xmlns:ot="http://uofm.org/objectteller/#"
 xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
  <rdf:Description rdf:about="http://uofm.org/objectteller/inputMessage">
    <ot:noofparams>1</ot:noofparams>
    <ot:params>
      <rdf:Seq>
        <rdf:li>rxcuisIn</rdf:li>
      </rdf:Seq>
    </ot:params>
  </rdf:Description>
  <rdf:Description rdf:about="http://uofm.org/objectteller/param/">
    <ot:datatype>STRING</ot:datatype>
  </rdf:Description>
</rdf:RDF>
```

```
# Example output RDF spec
 <rdf:RDF xmlns:ot="http://uofm.org/objectteller/"
  xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
  <rdf:Description rdf:about="http://uofm.org/objectteller/outputMessage">
    <ot:returntype>INT</ot:returntype>
  </rdf:Description>
</rdf:RDF>
```
