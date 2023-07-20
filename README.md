# Empirical Patterns from RDF Knowledge Graphs

This repository contains the code for extracting empirical ontology design patterns that emerge from (a portion of) a Knowledge Graph represented in RDF.

If you want to extract such patterns from Wikidata, please visit [the repository containing the code and the experiments for Wikidata](https://github.com/valecarriero/wikidata-empirical-patterns).

These patterns are expressed in the form of `< domain, property, range >` triplets, where `domain` is the type (`rdf:type`) of the subject and `range` is either the type of the object (when the object is a `resource`) or the `datatype`.

Each triplet is associated with the number of instances in the (sub-)KG that comply with that triplet, i.e. it is associated with its occurrences, and its frequentist probability, i.e. the ratio between the number of instances that are subject of at least one triple with that property and range, and the total number of instances.

These sets of triplets are then translated into OWL existential axiom, that are part of an OWL ontology design pattern.
Each axiom is annotated with its frequentist probability with respect to the specific pattern.
The patterns are expressed using [rdf-star](https://w3c.github.io/rdf-star/cg-spec/editors_draft.html) and relying on the [owl-star](https://github.com/cmungall/owlstar/blob/master/owlstar.ttl) vocabulary. 
Additionally, each set of triplets is transformed into a shape, associating each constraint with its probability value through comments. Shapes are expressed in [ShEx](https://shex.io/).
