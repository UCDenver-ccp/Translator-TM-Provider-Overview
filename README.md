# Translator-TM-Provider-Overview
Overview of the Translator Text Mining Provider prototype




# Milestone 1: BioStacks -- A framework facilitating layered annotation of the biomedical literature

![text](https://github.com/UCDenver-ccp/Translator-TM-Provider-Overview/blob/master/images/tm-provider-architecture.png "TM Provider architecture diagram")

## Design philospophy
### Infrastructure as code

### Modular service architecture


## Available services (Available via HTTP POST)
### Turku neural dependency parsing service

turku-neural-parser-svc-ipaddress       104.197.244.150

Example call of the Turku neural parsing service using cURL:
```
curl http://104.197.244.150 -X POST -d "This is an example sentence, nothing more, nothing less."
```

Results contain dependency parse information in the [CoNLL-U file format](https://universaldependencies.org/format.html).
```
# newdoc
# newpar
# sent_id = 1
# text = This is an example sentence, nothing more, nothing less.
1	This	this	PRON	DT	Number=Sing|PronType=Dem	5	nsubj	_	_
2	is	be	AUX	VBZ	Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin	5	cop	_	_
3	an	a	DET	DT	Definite=Ind|PronType=Art	5	det	_	_
4	example	example	NOUN	NN	Number=Sing	5	compound	_	_
5	sentence	sentence	NOUN	NN	Number=Sing	0	root	_	SpaceAfter=No
6	,	,	PUNCT	,	_	5	punct	_	_
7	nothing	nothing	PRON	NN	Number=Sing	5	appos	_	_
8	more	more	ADV	RBR	_	7	amod	_	SpaceAfter=No
9	,	,	PUNCT	,	_	5	punct	_	_
10	nothing	nothing	PRON	NN	Number=Sing	5	appos	_	_
11	less	less	ADJ	JJR	Degree=Cmp	10	amod	_	SpaceAfter=No
12	.	.	PUNCT	.	_	5	punct	_	SpacesAfter=\n
```

### OGER concept recognition service


oger-svc-chebi-ext-ipaddress            35.184.18.19
oger-svc-cl-ext-ipaddress               35.223.199.52
oger-svc-go-bp-ext-ipaddress            35.232.188.247
oger-svc-go-cc-ext-ipaddress            35.239.166.238
oger-svc-go-mf-ext-ipaddress            104.198.232.116
oger-svc-mop-ext-ipaddress              35.222.247.101
oger-svc-ncbitaxon-ext-ipaddress        34.71.49.58
oger-svc-pr-ext-ipaddress               34.71.72.164
oger-svc-so-ext-ipaddress               34.71.233.67
oger-svc-uberon-ext-ipaddress           34.71.229.56

Example call of the Cell type service using cURL:
```
curl -d "Blood cells and neurons are cool" http://35.223.199.52/upload/txt/tsv/12345
```

Results contain annotations of ontology concepts in the [BioNLP format](http://2013.bionlp-st.org/file-formats).
```
12345	cell	0	11	Blood cells	blood cell	CL:0000081		S1	CL_EXT
12345	cell	16	23	neurons	neuron	CL:0000540		S1	CL_EXT
```

## Results
### BioStacks
a BigQuery database facilitating storage of annotation layers for full text biomedical documnts

#### Example queries


### Text-mined knowledge graph
sentence co-occurrence as a proxy + Ignacio's results


#### Plan to achieve compliance with the Reasoner Standard API


# Milestone 2: NLP evaluation service for concept recognition systems
nlp-eval-svc-ipaddress                  35.193.207.6



## Criteria for inclusion
Containerized using Docker
Exposed REST API
License



# Milestone 3: Adaptive learning
Can show the BLUE samples as evidence of how this could work -- there are some relation extraction examples that show good performance.





# Scientific complementarity




# Relevant GitHub repositories
* [Translator TM Provider Infrastructure Modules](https://github.com/UCDenver-ccp/Translator-TM-Provider-Infrastructure-Modules)
  * Kubernetes cluster configuration files (Terraform)
  * Kubernetes service configuration files (Helm)
* [Translator TM Provider Infrastructure Live](https://github.com/UCDenver-ccp/Translator-TM-Provider-Infrastructure-Live)
  * Facilitates staging and production environments
* [Translator TM Provider Pipelines](https://github.com/UCDenver-ccp/Translator-TM-Provider-Pipelines)
 * Apache Beam pipelines used to populate 
* [Translator NLP Evaluation Service](https://github.com/UCDenver-ccp/Translator-nlp-eval-service)
