# Table of Contents

1. [General](#general)
2. [Literature Reviews](#reviews)
3. [Papers - Neural Networks](#papers_nn)
4. [Papers - Parse-based and statistical](#papers_traditional)
5. [Papers - Older papers and legacy systems ](#papers_old)
6. [Training and Testing Data](#data)

## General <a name="general"></a>

This README containts OpenIE and ORE papers and resources. Summaries are by [@jbecke](https://github.com/jbecke) and [@TheodoreChristakis](https://github.com/TheodoreChristakis), to the best of our abilities after reading each paper or testing the system (when available). We welcome pull requests with additional resources, papers, or data.

* [Wikipedia OpenIE](https://en.wikipedia.org/wiki/Open_information_extraction)

## Literature Reviews <a name="reviews"></a>

* [A Survey on Open Information Extraction](https://arxiv.org/abs/1806.05599). Most up-to-date literature review (June 2018), convering non-neural network based approaches to OpenIE. Whereas I've classified by age in this document, the authors classify by method of extraction (learning-based, rule-based, clause-based, inter-propositional).

* [Creating a Large Benchmark for Open Information Extraction](http://www.aclweb.org/anthology/D16-1252): summarizes the field and creates a benchmark for OpenIE systems and creates the first large benchmark dataset (note: not large enough to train NN's). 

* [Effectiveness and Efficiency of Open Relation Extraction](http://www.anthology.aclweb.org/D/D13/D13-1043.pdf): Review of the limited work done in the field of ORE (open relation extraction).

## Papers - Neural Networks <a name="papers_nn"></a>

* [Neural Open Information Extraction](https://arxiv.org/pdf/1805.04270.pdf): AFAIK, the first use of ANNs (seq2seq with attention) applied to OpenIE. Author bootstrapped tuples from high-confidence OpenIE-4 and makes the data available. However, the data isn't very clean; a quick glance shows a lot of malformed/incorrect tuples.

* [Supervised Open Information Extraction](http://aclweb.org/anthology/N18-1081): expands on the idea of turning QA datasets into OpenIE datasets. Trains an ANN with using an interesting feature representation, uses seq2seq model to generate BIO tags and then creates tuples from that using a deterministic algorithm.

* [Supervised Neural Models Revitalize the Open Relation Extraction](https://arxiv.org/pdf/1809.09408.pdf): tagging scheme similar to above paper, but uses a mixture of BiLSTM, CNN, and CRF and displays promising results.

* [Open Information Extraction from Question-Answer Pairs](https://arxiv.org/pdf/1903.00172v1.pdf) neural network to extract OpenIE tuples from conversation-based QA datasets.

*[Learning Open Information Extraction of Implicit Relations from Reading Comprehension Datasets
](https://arxiv.org/abs/1905.07471) extracting more implied ("common sense") relations.

## Papers - Parse-based and statistical <a name="papers_traditional"></a>

* [Graphene](https://www.researchgate.net/publication/325734922_Graphene_Semantically-Linked_Propositions_in_Open_Information_Extraction?enrichId=rgreq-810ff916f1de8d82406f9bc1738f5f61-XXX&enrichSource=Y292ZXJQYWdlOzMyNTczNDkyMjtBUzo2MzY5NTQ2MzkwODU1NzFAMTUyODg3MzIyODAxNg%3D%3D&el=1_x_3&_esc=publicationCoverPdf) generates n-ary extractions with semantically linking-labels like "TEMPORAL", "CAUSE", etc. as well as open relations
* [Stanford Open IE](https://nlp.stanford.edu/software/openie.html): produces maximally-shortened tuples. It seems to often produce tuples for which the reported confidience is often 1.0. GPL or proprietary available as part of [Stanford Core NLP](https://stanfordnlp.github.io/CoreNLP/).
* [OpenIE-X](https://knowitall.github.io/openie/) ([v4](https://github.com/knowitall/openie), [v5](https://github.com/dair-iitd/OpenIE-standalone), [allen institute version](https://github.com/allenai/openie-standalone)). Works well with simple statements (see examples [in this dataset](http://data.allenai.org/tuple-ie/)). Outputs context for extractions and gives good confidence predictions that can be used to balance precision-recall. Note the restrictive license (research purposes only). 
* [Open Relation Extraction and Grounding](http://aclweb.org/anthology/I17-1086): Extracts argument pairs of relation tuples and forms weighted dependency trees between two arguments. It shows promising results in determining relative importance of each argument in the tree.
* [Unsupervised Open Relation Extraction](https://arxiv.org/pdf/1801.07174.pdf): Used for unsupervised relation extraction from free text by using pretrained word embeddings while using a sentence's dependency parse tree as a foundation.


## Papers - Older papers and legacy systems <a name="papers_old"></a>

* From University of Washington
  * [TextRunner](http://turing.cs.washington.edu/papers/ijcai07.pdf) - One of the earliest papers addressing open information extraction
  * [Reverb](http://reverb.cs.washington.edu/) - Improved the extraction to better form the tuple of (argument, relation, argument)
  * [OLLIE](https://knowitall.github.io/ollie/) - Addressed the issue of misleading propositions and non-verb mediated relations
* [CSD-IE](https://ieeexplore.ieee.org/document/6693511/) - Generation of nested contractions which is especially effective in sentences using subordinating clauses
* [PropS](http://u.cs.biu.ac.il/~stanovg/props.html): Syntax Based Proposition Extraction
* [ClausIE](https://www.mpi-inf.mpg.de/departments/databases-and-information-systems/software/clausie/) - Formed a strong relation between grammatical clauses, propositions, and OIE extractions by defining seven grammatical patterns
* [ReNoun](http://www.aclweb.org/anthology/D14-1038) - Used predominantly for noun-mediated relations.


## Training and Testing Data <a name="data"></a>

* [35M sentence-tuple pairs](https://onedrive.live.com/?cid=c826c2d6f4c7d993&id=C826C2D6F4C7D993%213193&authkey=!AHj1kHDE5TSS0e8): from the paper [Neural Open Information Extraction](https://arxiv.org/pdf/1805.04270.pdf). It was generated by OpenIE-4, removing any tuples less then 0.9 confidence. Because there is no sample data, I've copied a bit below. As you can see, the data is somewhat noisy. It *might* be useful for extra training data, but not as a gold dataset. 
```
* moving and handling '' ' - a comprehensive course that covers safe handling and transport of casualties .
<arg1> '' ' - a comprehensive course </arg1> <rel> covers </rel> <arg2> safe handling and transport of casualties </arg2>

this word , adjectival magavan meaning `` possessing maga - '' , was once the premise that avestan maga - and median magu - were co-eval .
<arg1> - '' , was once the premise that avestan maga - and median magu - </arg1> <rel> were </rel> <arg2> co-eval </arg2>

melora walters as candy ' - a hooker who works for the motel where john person is staying , as a complimentary service to the guests .
<arg1> ' - a hooker </arg1> <rel> works </rel> <arg2> for the motel </arg2>

- - a hunter who uses bows and arrows instead of guns .
<arg1> - - a hunter </arg1> <rel> uses </rel> <arg2> bows and arrows instead of guns </arg2>
```

* [TupleInf Open IE Dataset](http://data.allenai.org/tuple-ie/): OpenIE-4 extractions of 8th grade and 4th grade questions. By inspection, these tend to be cleaner than the above dataset because of the simplicity of the language. Confidence-values are retained so you can make your own tradeoff between precision and recall. Note suitable for a gold dataset.
```
01 April 1969 The ATM would be a manned solar observatory making measurements of the Sun by telescopes and instruments above 
0.96 (The ATM; would be; a manned solar observatory making measurements of the Sun by telescopes and instruments)
0.93 (a manned solar observatory; making; measurements of the Sun)

01 April 1969 The ATM would be a manned solar observatory making measurements of the Sun by telescopes and instruments above the Earth's atmosphere.
0.96 (The ATM; would be; a manned solar observatory making measurements of the Sun by telescopes and instruments above the Earth's atmosphere)
0.93 (a manned solar observatory; making; measurements of the Sun)

01 - Compare the physical properties of ice, liquid, water, and vapor.

01 Earthly Seasons PURPOSE: To show that the seasons are the consequence of the tilt of earth.

0.1% water can lower the melting temperature of peridotite by 100 C.
0.91 (0.1% water; can lower; the melting temperature of peridotite)

( 020 ) Celsius &#176;C The international temperature scale where water freezes at 0 (degrees) and boils at 100 (degrees).
0.89 (water; freezes; at 0 (degrees)
```
* [Squadie](https://github.com/NPCai/Squadie) (not yet published, expect changes): this is our dataset derived from Squad. It uses a similar JSON format to SQuAD and contains 50,000 tuples. This tuple can then be matched with the corresponding sentence in the training corpus. Not suitable as a gold corpus. Squadie is useful for extracting implied relations. We have also converted Maluuba NewsQA.
```
                        {
                            "question": "Which film did Beyoncé star in 2001 with Mekhi Phifer?",
                            "id": "56d4831f2ccc5a1400d83155",
                            "answer": "Carmen: A Hip Hopera",
                            "tuple": "<Which film\tdid Beyoncé star with Mekhi Phifer\tCarmen: A Hip Hopera>"
                        },
                        {
                            "question": "What was the name of Destiny Child's third album?",
                            "id": "56d4831f2ccc5a1400d83156",
                            "answer": "Survivor",
                            "tuple": "<Survivor\tthe name of\tDestiny Child 's third album>"
                        },
                        {
                            "question": "Who filed a lawsuit over Survivor?",
                            "id": "56d4831f2ccc5a1400d83157",
                            "answer": "Luckett and Roberson",
                            "tuple": "<Luckett and Roberson\tfiled a lawsuit over\tSurvivor>"
                        },
                        {
                            "question": "When did Destiny's Child announce their hiatus?",
                            "id": "56d4831f2ccc5a1400d83158",
                            "answer": "October 2001",
                            "tuple": "<Destiny 's Child\tannounce their hiatus\tOctober 2001>"
                        }
```
