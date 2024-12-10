---
name: Daily Checklist
about: Steps necessary to check the full index and other data loads
title: 'Daily checklist: '
labels: Full Index, Data loads, Assertion Sync and Image Service
assignees: ''

---
Every day:

-  monitor the index switch 
-  all scheduled jobs for the day completed successfully (raise on Slack if not) 
-  assertions sync has run ( ie check user assertion counts are in DQ Profile)
-  images processing is progressing and not stalled
-  check there are no long-running (ie > 24 hours) clusters (filter on Running state)
-  clear biocache cache (has to be done after assertion sync and index successfully switched)

Raise any issues on the data management internal channel 

- [x] Monday
- [x] Tuesday
- [x] Wednesday
- [x] Thursday
- [x] Friday


Once a week (whenever):
-  sensitive data check (script in GitHub)

## Job Schedule

[Scheduled jobs - Github config](https://github.com/AtlasOfLivingAustralia/databox/blob/master/airflow/pipelines-job-schedules/job-schedule-config-prod.json) 

**Daily**
| Time | Job | Job Name|
| --- | --- | --- |
| 3am | Index to SOLR |
| 7am | OBIS | dp5183-obis-weekly|


**Weekly**
| Day | Time | Job |DR | Job Name|
| --- | --- | --- | --- | --- |
| Mon | 12am | BIS Weeds  | dr27665|  dr27665-BISFetcher-weekly
| Mon | 7am | iNaturalist | dr1411| dr1411-inaturalist-weekly |
| Mon | 7pm | FeralScan | dr19813 | dr19813-feralscan-weekly |
| Tue | 12am | Mel AVH | dr13282 | dr13282-mel-avh-weekly|
| Tue | 9am | cPlatypus | dr7973 | dr7973-cplatypus-weekly |
| Tue | 9am | APII | dr413 | dr413-apii-weekly |
| Tue | 9am | Butterflies Aust | dr16457 |  dr16457-butterflies-weekly|
| Tue | 5pm | Biocollect | dp3903 | dp3903-biocollect-weekly |
| Tue | 8pm | Bionet | dr368 |  dr368-bionet-weekly |
| Wed | 12am | Perth AVH | dr15863 | dr15863-perth-avh-weekly |
| Wed | 8am | Questagame | dr1902| dr1902-questagame-weekly |
| Wed | 9am | NatureMapr | dr19123 |  dr19123-naturemapr-weekly |
| Wed | 1pm | QM | dr344 | dr344-QM-weekly |
| Thu | 12am | CANB AVH | dr15860 |  dr15860-canb-avh-weekly|
| Thu | 12.25am | CNS AVH | dr15867 | dr15867-cns-avh-weekly  |
| Thu | 12.40am | JCT AVH | dr15868 | dr15868-jct-avh-weekly |

**Monthly**
| Day | Time | Job | DR | Job Name |
| --- | --- | --- |  --- | --- |
| First Thu | 5.15pm | MV | dr342 | dr342-MV-monthly |
| First Wed | 9am | TurtleSat | dr26141 | dr26141-turtleSat-monthly |
| First Wed | 9am | UC Genomics | dr25075 | dr25075-UCGenomics-monthly |
| 5th | 12am | UniMelb AVH | dr13282 | dr13282-melu-avh-monthly |
| 5th | 12am | Hobart AVH  | dr10574 | dr10574-ho-avh-monthly |
| 6th | 12am | Allan Herbarium | dr27654| dr27654-chr-avh-monthly |
| 6th | 12.01am | WELT AVH | dr26642 | dr26642-welt-avh-monthly |
| 6th | 12.15am | Auckland Museum Botanical  | dr26650 | dr26650-ak-avh-monthly |
| 6th | 12.45am | NZ PDD | dr26651| dr26651-pdd-avh-monthly |
| 19th | 12am | NSW AVH | dr15861 | dr15861-nsw-avh-monthly|
| 20th | 12am | BRI AVH | dr2287| dr2287-bri-avh-monthly |
| 21st | 12am | AD AVH | dr15865 | dr15865-ad-avh-monthly | 
