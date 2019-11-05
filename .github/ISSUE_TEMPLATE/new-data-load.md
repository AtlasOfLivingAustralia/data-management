---
name: New data load
about: Steps necessary for new data loads
title: 'Load data : '
labels: Data Load
assignees: ''

---

- [ ] After creation, add this issue to the Data Management project board https://github.com/orgs/AtlasOfLivingAustralia/projects/9

- [ ] Ask data provider for metadata, including:
* Data resource name
* Description
* License : prefer Creative Commons Attribution https://creativecommons.org/licenses/by/4.0/
* Citation : Statement to be used by those downloading and using these records
* Contact : Email and/or phone number
* Website : (Optional)
- [ ] Map dataset to Darwin Core Terms if necessary http://rs.tdwg.org/dwc/terms/
- [ ] Create new data resource using https://collections.ala.org.au/admin
- [ ] Upload the dataset to collections.ala.org.au
- [ ] Load/sample/process dataset http://aws-scjenkins.ala:9193/job/Parameterised%20Load%20Sample%20Process/ 
- [ ] Note the statistics for total and new records from the end of the log file for the load by pasting the relevant lines here:
```
[Log entries..... ]
```
- [ ] Wait for next complete reindex
- [ ] Check that the number of records accessible match the loaded numbers using https://biocache.ala.org.au/occurrence/search?q=data_resource_uid:drNNN
- [ ] Ask the data provider to review the new records using the same URL
