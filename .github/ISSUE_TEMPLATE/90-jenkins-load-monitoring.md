---
name: Jenkins - Automated Data Load Monitoring
about: List of jobs to monitor each week
title: "Monitor Data Loads : "
labels: Data Load
assignees: ''
---

- [ ] After creation, add this issue to the Data Management project board https://github.com/orgs/AtlasOfLivingAustralia/projects/9

**Jenkins Access**
- **SSH:**   ssh -L 9194:127.0.0.1:9194 aws-spark-quoll-master.ala
- **Data resource loads:** http://aws-spark-quoll-master.ala:9194/job/Data-resource-loads/
- **GBIF Loads:** [http://aws-spark-quoll-master.ala:9194/job/](http://aws-spark-quoll-master.ala:9194/job/Data-resource-loads/)GBIF

**Reference**
- **Jenkins - Automated Data Load Schedule:** https://confluence.csiro.au/display/ALASD/Jenkins+-+Automated+Data+Load+Schedule

***
**Monitoring Schedule**  - automated jobs are to be monitored twice per week on **Tuesday** and **Friday**.  

Please enter Week commencing date: 22/08/2022

**Tuesday Monitoring**

**Data-resource-loads** folder:
 - [ ]  dp3903-biocollect-monthly 
 - [ ]  dr1411-inaturalist-weekly    
 - [ ]  dr15863-perth-avh-weekly  
 - [ ]  dr1902-questagame-weekly      
 - [ ]  dr368-bionet-weekly-delta  
 - [ ]  dr376-mel-avh-weekly
     

**Friday Monitoring**

**GBIF** folder:
 - [ ]  Dwca-export-all      
 - [ ]  Dwca-package-for-gbif-all   

**Data-resource-loads** folder:
 - [ ]  dr10574-ho-avh-weekly    
 - [ ]  dr15860-canb-avh-weekly   
 - [ ]  dr15867-cns-avh-weekly
 - [ ]  dr15868-jct-avh-weekly 
 - [ ]  dr2153-nzvh-avh-weekly 
 - [ ]  dr341-canb-anwc-weekly 
 - [ ]  dr7973-cPlatypus-weekly  


There are also quarterly and monthly jobs that will need to be checked on the following days of the month:

**3rd of month quarterly - Feb, May, Sept, Nov**
 - [ ]   dr365,dr366-BDBSA-quarterly

**5th day of month** 
 - [ ]   dr344-qm-full-load-monthly

**28th day of month**
 - [ ]   dp5183-obis-seamap-monthly 





