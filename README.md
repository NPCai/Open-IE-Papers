# Open-IE-Papers

Open Information Extraction (OpenIE) papers and resources. Summaries are by Jacob Beckerman, to the best of my ability after reading each paper or testing the system (when available). Some links are duplicated accross sections such that each section is self-contained.

## General

* [Wikipedia OpenIE](https://en.wikipedia.org/wiki/Open_information_extraction)

## Literature Reviews

* [Creating a Large Benchmark for Open Information Extraction](http://www.aclweb.org/anthology/D16-1252): summarizes the field and creates a benchmark for OpenIE systems
* 

## Papers - Neural Networks

* [Neural Open Information Extraction](https://arxiv.org/pdf/1805.04270.pdf): AFAIK, the first use of ANNs (seq2seq with attention) applied to OpenIE. Author bootstrapped tuples from high-confidence OpenIE-4 and makes the data available. However, the data isn't very clean; a quick glance shows a lot of malformed/incorrect tuples.
* [Supervised Open Information Extraction](http://aclweb.org/anthology/N18-1081): expands on the idea of turning QA datasets into OpenIE datasets. Trains an ANN with using an interesting feature representation, uses seq2seq model to generate BIO tags and then creates tuples from that using a deterministic algorithm.

## Papers - Other Methods

* [Stanford Open IE](https://nlp.stanford.edu/software/openie.html): it's great for maximally-shortened tuples. Cons: it seems to often produce nonsensical tuples for which the reported confidience is often 1.0.

## People

## Data

## Systems

## Repositories
