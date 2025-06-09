---
name: BDBSA Uploads
about: Steps necessary for BDBSA data loads
title: 'BDBSA Data Load: '
labels: Data Load, FreshDesk
projects: AtlasOfLivingAustralia/21
---


**<date>**

**Support Request:** https://support.ehelp.edu.au/a/tickets/xxx

The SA Department for Environment and Water sends two zip files to ALA uploads:
 	s3://ala-uploads-source-data-production/uploads-server-sync/dewnr-sa/upload/dewnr-sa/
for `SA Flora` and `SA Fauna`.

These 2 zip files contain data data for 3 dataresources

| File | Dataresource | DR name | URL |
| ---- | ------------ | ------- | --- |
| safauna.zip | dr365  | SA Fauna | https://collections.ala.org.au/dataResource/show/dr365  |
| safauna*.zip| dr10043| Frogwatch SA  | https://collections.ala.org.au/dataResource/show/dr10043 |
| saflora*.zip| dr366 | SA Flora | https://collections.ala.org.au/dataResource/show/dr366 |

The **BDBSA** fetcher processes all 3 dataresources. It determines the correct file to download based on file prefix values defined in `config.py` and downloads the latest version in the uploads directory. 

**Note:** The collectory `Data URL` in `Connection Paremeters` does not require the zip file as part of the URL.


**Steps**
Run preingestion separately for each of these dataresources
- [ ] Databox
- [ ] Prod
- [ ] Update data currency dates in `Data Mobilisation` section in Collectory DR

![alt text](image.png)

| Dataresource            | Last checked to | Data currency to |
| ----------------------- | ----------------| ---------------- | 
| dr365 - SA Fauna        | 2025-03-20 00:00:00.0 | 2025-03-20 00:00:00.0  |
| dr366 - SA Flora        | 2025-03-21 00:00:00.0  | 2025-03-20 00:00:00.0 |
| dr10043 - Frogwatch SA  | 2025-03-20 00:00:00.0 | 2025-03-20 00:00:00.0  |

**Record Counts**
| Dataresource           | Old | New | Difference |
| ---------------------- | --- | --- | -----------|
| dr365 - SA Fauna       |     |     |            |
| dr366 - SA Flora       |     |     |            |
| dr10043 - Frogwatch SA |     |     |            |

