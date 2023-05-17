---
name: Daily weekday full index to solr checks
about: Steps necessary to check full index
title: 'Full index to solr checks : '
labels: Full index
assignees: ''

---

**Check**
- [ ] Go to emr cluster list. Filter by Full_index_to_SOLR ala-prod-pipelines-airflow. Look for the lastest index run cluster.
      If cluster shows "Terminated" as status and "All steps completed", perform Successful checking step.
      If the cluster shows "Terminated with errors" as status, open the cluster, perform Error checking step.

**Successful checking step**
- [ ] Perform sanity check by checking biocache for the latest occurrence record counts. Also check images and assertion numbers. Optionally, tunnel into solr to check the previous solr collection for the record count.
- [ ] Report the error on data-management internal channel that index run is successful today

**Error checking step**
- [ ] Check error on the Steps tab. On the Step that error, open the stdout or stderr link. Check the error.   
- [ ] Report the error on data-management internal channel. Paste the error log if possible on slack. 
- [ ] If the error has to do with index checking step, and it's acceptable to switch, tunnel into solr using the following command: 
```
ssh -L 8983:localhost:88983 aws-solr-2021-1.ala
```
- [ ] Delete the biocache alias and create a new biocache alias and point it to the new solr collection that has been created by the full index to solr cluster.
- [ ] Check for disk space in solr clusters in the UI. Make sure there's at least 70% of disk space. Otherwise, delete the old solr collection. 
