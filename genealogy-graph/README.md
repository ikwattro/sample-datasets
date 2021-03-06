**WARNING**: This project is a legacy one that is no longer actively maintained. It is superseded by example code that is used throughout the GRAKN.AI documentation. To find out more, it is best to go to the [Quickstart Tutorial](https://grakn.ai/pages/documentation/get-started/quickstart-tutorial.html).

When this example project was initially created, it was described in more detail at https://medium.com/@doctormiko/1bb639396a24#.becpcqqi1. Syntax changes mean that the article is no longer working, but the concepts are still valid, and a good starting point for those wanting to learn more about GRAKN.AI.  We recommend that you look at the full [documentation](https://grakn.ai/pages/index.html) for up-to-date information and [blog](https://blog.grakn.ai) for additional tutorials.


## ontology.gql
   
For the ontology, I took inspiration from the [Gedcom X specifications](http://www.gedcomx.org) (albeit with simplification, so the ontology is only loosely inspired by it).
    
The general idea of the ontology is that, to build your family tree, you gather documents that will serve as evidence for different occurrences (births, deaths, marriages etc.). Once an event is supported by enough evidence, the connected knowledge can be transferred to the actual family tree. 

To load the ontology, make sure you have downloaded Grakn and started the Grakn engine (see our [setup guide](https://grakn.ai/pages/documentation/get-started/setup-guide.html) if you need more information about how to do this). Then, from the terminal: 

```
../bin/graql.sh -f ./ontology.gql
```

## basic-ontology.gql

This is the basic ontology without any definitions for elements that can be inferred by Grakn. It is used by an example that illustrates CSV migration from the CSV files in the `/raw-data` directory, but should not be used for the full genealogy-graph demo.

## data.gql
   
The data here is taken, with some modification, from the family relationships described in the [Lenzen Research paper](http://www.lenzenresearch.com/titusnarrlineage.pdf) entitled "The Maternal Line of Elizabeth (Niesz) Titus". (The data is in Graql format as a result of migration of the raw CSV data files, found in the /raw-data folder, using the loader.sh script therein.

Load the data:
```
../bin/graql.sh -f ./data.gql
```


## rules.gql

A set of rules for the Grakn reasoner.

```
../bin/graql.sh -f ./rules.gql
```