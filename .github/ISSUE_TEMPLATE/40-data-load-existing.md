---
name: Data Load - Existing Data Resource
about: Steps necessary for existing data loads where the data resource has already been created and there is data previously uploaded to the ALA
title: 'Merge Data Load :'
labels: Data Load
assignees: ''

---

- [ ] After creation, add this issue to the Data Management project board https://github.com/orgs/AtlasOfLivingAustralia/projects/9

**Metadata**
- [ ] Locate the existing data resource in the collectory and check metadata and parameters: https://collections.ala.org.au/dataResource/show/drNNNN 
- [ ] Check the unique identifier matches that in the new dataset

**Data Prep**
- [ ] Map dataset to Darwin Core Terms in a CSV if necessary http://rs.tdwg.org/dwc/terms/. Package the CSV into a Darwin Core Archive
- [ ] Ensure the dataset has correctly specified unique identifier without duplicates, and matches the unique identifier in the collectory connection parameters
- [ ] Ensure images are specified in an images file in the DwCA with the identifier field populated
- [ ] Check that species, location, times are adequately specific. Check back with the data provider if necessary
- [ ] Download existing DwCA from hdfs and merge the two DwCAs 

**Data Load**
- [ ] Upload the new DwCA to the dmgt server
- [ ] Run the Ingest_dataset job on Jenkins, setting the data resource UID (DRNNNN) parameter http://aws-spark-quoll-master.ala:9194/job/Ingest-dataset/
- [ ] Note the statistics for total and new records from the end of the log file for the load by pasting the relevant lines here:
```
[Log entries..... ]
```
**QA**
- [ ] Wait overnight for next complete reindex
- [ ] Check that the number of records accessible match the loaded numbers using https://biocache.ala.org.au/occurrence/search?q=data_resource_uid:drNNNN
- [ ] Ask the data provider to review the new records using the same URL
