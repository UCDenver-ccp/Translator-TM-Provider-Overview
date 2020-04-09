# Sample knowledge graph

The sample knowledge graph (KG) provided was mined from ~4000 Pubmed Central Open Access articles using concepts from 10 Open Biomedical Ontologies. Nodes in the KG represent ontology concepts. The KG uses concept cooccurrence in sentences as a proxy for relations between the concepts. Note that future versions of this KG will use explicit relations between concepts, but the initial proposal was to use sentence cooccurrence of concepts as a relationship proxy in the interim. Edges, therefore, indicate that the connected concepts were observed in at least one sentence in the corpus of articles. Each edge contains metadata indicating from which articles the cooccurrence relation was mined. 

## JSON schema for sample knowledge graph
The knowledge graph is serialized using a simple JSON graph representation (see [JSON schema file](https://github.com/UCDenver-ccp/Translator-TM-Provider-Overview/raw/master/sample-files/kg-schema.json)). Nodes represent ontology concepts that were observed in the text-minded articles. Edges between nodes indicate concepts that were observed to cooccur in the same sentence, and contain an evidence property to store document provenance.

