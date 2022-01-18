---
name: Data Load - New Data Resource
about: Steps necessary for completely new data loads
title: 'New Data Load : '
labels: Data Load
assignees: ''

---

- [ ] After creation, add this issue to the Data Management project board https://github.com/orgs/AtlasOfLivingAustralia/projects/9

**Metadata**
- [ ] Ask data provider for metadata, including:
* Data resource name
* Description
* License : prefer Creative Commons Attribution https://creativecommons.org/licenses/by/4.0/
* Citation : Statement to be used by those downloading and using these records
* Contact : Email and/or phone number
* Other fields as necessary
- [ ] Using the metadata, create a new data resource using https://collections.ala.org.au/admin
- [ ] Ensure the correct connection parameters are specified at https://collections.ala.org.au/dataResource/show/drNNNN (Unique identifiers! Protocol!) 

**Data Prep**
- [ ] Map dataset to Darwin Core Terms in a CSV if necessary http://rs.tdwg.org/dwc/terms/. Package the CSV into a Darwin Core Archive
- [ ] Ensure the dataset has correctly specified unique identifier without duplicates
- [ ] Ensure images are specified in an images file in the DwCA with the identifier field populated
- [ ] Check that species, location, times are adequately specific. Check back with the data provider if necessary

**Data Load**
- [ ] Upload the DwCA to collections.ala.org.au or onto the dmgt server
- [ ] Run the Ingest_dataset job on Jenkins, setting the data resource UID (DRNNNN) parameter http://aws-spark-quoll-master.ala:9194/job/Ingest-dataset/
- [ ] Note the statistics for total and new records from the end of the log file for the load by pasting the relevant lines here:
```
[Log entries..... ]
```
**QA**
- [ ] Wait overnight for next complete reindex
- [ ] Check that the number of records accessible match the loaded numbers using https://biocache.ala.org.au/occurrence/search?q=data_resource_uid:drNNNN
- [ ] Ask the data provider to review the new records using the same URL

Other checks
- [ ] [Optional] Should we run through the process using Databox first?
- [ ] [Optional] If the dataset is destined to be included in a data hub, identify the data hub and add the new data resource id to its list https://collections.ala.org.au/dataHub/list
- [ ] [Optional] Is it a collection? Make sure the provider map in the collectory (https://collections.ala.org.au/providerMap/list) works such that collectionCode and institionCode in the source data map to the right collection
