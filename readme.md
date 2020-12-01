# Steps to download metadata from OpenData Matera
The open data Matera Web Portal, http://dati.comune.matera.it/ is compliant with DCAT-AP-IT and deploys a CKAN web portal RDF enabled.

## 1- Downloading the whole catalog
Instructions are available at https://github.com/ckan/ckanext-dcat#rdf-dcat-harvester
-  to download all the catalog, we can access http://dati.comune.matera.it/catalog.ttl and save it as  OpenMateraDatasetCatalog.ttl


## 2- Preparing a SPARQL query to get the info in a CSV
2.1 Yasgui https://yasgui.triply.cc/ provides a GUI for checking syntax and writing SPARQL queries.
2.2 query available on GenerateDatasetwithDistributionFromDCAT.sparql


## 3- Query the RDF store generating one or more CVS with the DCAT-AP-IT descriptions.
Jena provides a tool for querying via SPARQL, see instruction https://jena.apache.org/documentation/tools/


```
sparql --data OpenMateraDatasetCatalog.ttl   -query GenerateDatasetwithDistributionFromDCAT.sparql --results=TSV > OpenMateraDatasetCleanedDistribution.csv
```

## 4- Importing the CVS in Excel
The excel file OpenMateraDatasetCleanedDistribution.xlsx  is generated via CSV importing with tab delimiters.
