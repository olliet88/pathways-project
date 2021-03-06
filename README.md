# PathLink

This is the repository containing my 3rd year project research.

## Motivation

There is a significant amount of bioinformatic data available in different formats and places.

This is fine for manual use but even then it is lengthy to use the data to come to any conclusions.

The purpose of this project is to provide an API and graphical interface which provides quick access to cancer-related bioinformatic data along with other data computed from:

* KEGG
* Pathway Commons
* CIViCDB
* ClinVar
* UniProt
* STRING

The system will also provide an API to produce comprehensive Neo4j representations of all KEGG pathways - along with mechanisms for enrichment and other analysis.

## Structure

### Preliminaries

These are the files and programs I used for my preliminary research into the Biological Pathways domain prior to the full system design

### System

This is the cumulative result of the work so far with a frontend Flask webserver and a REST-style API.

This frontend accepts structured queries fulfilling the criteria set out in the report.

For more information about running the system, consult System/README.md

### Testing

This contains any script used to test the system as an outsider.