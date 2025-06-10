
<h3> BDBSA Data Load</h3>

**Labels:** `Data Load`, `FreshDesk`

**<date>**

**Support Request:** https://support.ehelp.edu.au/a/tickets/xxx

The SA Department for Environment and Water sends two zip files for `SA Flora` and `SA Fauna` to ALA uploads:
 
    uploads-server-sync/dewnr-sa/upload/dewnr-sa/

These 2 zip files contain data data for 3 dataresources

| File | Dataresource | DR name | URL |
| ---- | ------------ | ------- | --- |
| saflora*.zip| dr366 | SA Flora | https://collections.ala.org.au/dataResource/show/dr366 |
| safauna.zip | dr365  | SA Fauna | https://collections.ala.org.au/dataResource/show/dr365  |
| safauna*.zip| dr10043| Frogwatch SA  | https://collections.ala.org.au/dataResource/show/dr10043 |

The **BDBSA** fetcher processes all 3 dataresources. It determines the correct file to download based on file prefix values defined in `config.py`and downloads the latest version.  

**Note:** The collectory `Data URL` in `Connection Paremeters` does not require the zip file as part of the URL.

<h3>Load Steps</h3>

1. Run preingestion/load separately for each dataresources
 - [ ] Databox
 - [ ] Prod

2. Update data currency dates in `Data Mobilisation` section in Collectory DR
 - [ ] Databox
 - [ ] Prod

![image](https://github.com/user-attachments/assets/95304042-6d4b-49c6-904d-3d627ac96c70)


<h3>Load results</h3>

| Dataresource            | Last checked to | Data currency to |
| ----------------------- | ----------------| ---------------- | 
| dr365 - SA Fauna        | |   |
| dr366 - SA Flora        |   |  |
| dr10043 - Frogwatch SA  |  |   |

**Record Counts**
| Dataresource           | Old | New | Difference |
| ---------------------- | --- | --- | -----------|
| dr365 - SA Fauna       |     |     |            |
| dr366 - SA Flora       |     |     |            |
| dr10043 - Frogwatch SA |     |     |            |

