---
name: Data Load - New Data Resource
about: Steps necessary for completely new data loads
title: 'New Data Load : '
labels: Data Load
projects: AtlasOfLivingAustralia/21
---
**Metadata**
- [ ] Ask data provider for metadata, including:
* Data resource name
* Description
* License : prefer Creative Commons Attribution https://creativecommons.org/licenses/by/4.0/
* Citation : Statement to be used by those downloading and using these records
* Contact : Email and/or phone number
* Other fields as necessary
- [ ] Using the metadata, create a new data resource in collectory TEST & PROD
- [ ] Ensure the correct connection parameters are specified at the DR (Unique identifiers! Protocol!) `Custom Web Service` used as the protocol for Fetchers

**Data Prep**
- [ ] Map dataset to Darwin Core Terms in a CSV if necessary http://rs.tdwg.org/dwc/terms/. 
- [ ] Link Pull Request to this issue (Either PR on databox or a fetcher in Preingestion)
- [ ] Ensure the dataset has correctly specified unique identifier without duplicates
- [ ] Ensure images are specified in an images file in the DwCA with the identifier field populated
- [ ] Check that species, location, times are adequately specific. Check back with the data provider if necessary

**Data Load**
- [ ] Do a test load on data-box, check for:
    - [ ] Total number of records
    - [ ] UUIDs
    - [ ] Sensitive records
    - [ ] Quality Filters
- [ ] Note the statistics for total and new records from UUID step of the ingest here:
```
[Log entries..... ]
```
- [ ] Ask the data provider to review the records using Databox URL
- [ ] Load the dataset in the production environment after getting feedback from the data provider 
- [ ] Note the statistics for total and new records from UUID step of the ingest here:
```
[Log entries..... ]
```
- [ ] inform the data provider that the dataset has been loaded successfully in production with a URL to the records

Other checks
- [ ] [Optional] Should we run through the process using Databox first?
- [ ] [Optional] If the dataset is destined to be included in a data hub, identify the data hub and add the new data resource id to its list https://collections.ala.org.au/dataHub/list
- [ ] [Optional] Is it a collection? Make sure the provider map in the collectory (https://collections.ala.org.au/providerMap/list) works such that collectionCode and institionCode in the source data map to the right collection


Close the ticket as completed after all the subtasks are ticked off.
