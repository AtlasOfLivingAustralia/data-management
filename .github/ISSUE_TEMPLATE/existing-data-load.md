---
name: Data Load - Existing
about: Steps necessary for existing data loads
title: 'Data load :'
labels: Data Load
assignees: ''

---

- [ ] After creation, add this issue to the Data Management project board https://github.com/orgs/AtlasOfLivingAustralia/projects/9

- [ ] Map dataset to Darwin Core Terms if necessary http://rs.tdwg.org/dwc/terms/
- [ ] Upload the dataset to collections.ala.org.au
- [ ] Load/sample/process dataset http://aws-scjenkins.ala:9193/job/Parameterised%20Load%20Sample%20Process/ 
- [ ] Note the statistics for total and new records from the end of the log file for the load by pasting the relevant lines here:
```
[Log entries..... ]
```
- [ ] Wait for next complete reindex
- [ ] Check that the number of records accessible match the loaded numbers using https://biocache.ala.org.au/occurrence/search?q=data_resource_uid:drNNN
- [ ] Ask the data provider to review the new records using the same URL
