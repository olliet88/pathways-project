# Preliminaries

## Dependencies

To get all the dependencies for this project run 

```
pip install -r requirements.txt
```

In this directory (`/Preliminaries`)
## Pathway_participation

This module is for establishing a Protein's participation.

Specific participation can be verified as such:

```
python3 -m Pathway_participation.participation_check "PARP1" "Base excision repair"
```

This would query the Pathway Commons and KEGG datasets to establish whether PARP1 participates in the Base excision repair pathway.

A list of pathways participated in can be printed using:

```
python3 -m Pathway_participation.all_pathways "PARP1"
```

## KGML2Neo4j

Given a pathway name this will convert and send the information stored in
KEGG to a Neo4j database.

### Usage

This expects a server_config file in the directory of execution in the form:

```
[KGML2NEO4J]
username = neo4j
password = example
uri = [uri here - usually neo4j://localhost:...]
```

The program is executed as such (this is from the Preliminaries directory):

```
python3 -m KGML2Neo4j.main [pathway name]
```

e.g:

```
python3 -m KGML2Neo4j.main "colorectal cancer"
```

### Example queries on the Neo4j database

The following queries are all in cypher - the query language supported by Neo4j databases.

This also assumes the "colorectal cancer" example has been used to populate the database.

This query will retrieve all paths including and succeeding any nodes with the name "hsa:3845".
This node refers to the "KRAS" Gene.
```
MATCH path = (a)-[*1..]->()
WHERE "hsa:3845" in a.name
RETURN path
```

