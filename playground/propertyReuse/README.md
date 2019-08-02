# Property reuse

In the Semantic world, you "cannot" define more domains for the same property. Formally, you can, but "in RDF, multiple domains are defined to have intersection semantics" (see [here](https://stackoverflow.com/a/23729566/4820341))

Possible solutions:

- turn the reasoner off (_sigh_)

- create common superclasses (_cumbersome_ and sometimes meaningless)

- use `owl:unionOf` (OWL Lite+)

```SPARQL
las:myProperty rdfs:domain [

  a owl:Class ;
  owl:unionOf ( las:Bioentity las:Contanier las:Foo )

] .
```



