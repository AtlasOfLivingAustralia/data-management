---
name: Soft Delete DataResource 
about: Steps necessary for deleting a dataResource 
title: 'Delete a DataResource: '
labels: Soft Delete DataResource
assignees: ''

---
### Task:Soft Delete dr and Synchronize Collectory with GBIF

**Description:**  Link the dataset in GBIF to be deleted to the dataset it will be superceded by

[ ] Go to the registry.gbif.org/ entry for the dataset (eg here [https://registry.gbif.org/dataset/eebc1080-cec1-4d28-a5d3-ba8694114d12])
[ ] Edit and set the 'Duplicate of Dataset' to the new dataset uuid (maybe the parent one needs to be set as well)
  

**Description:**  Perform the following steps to delete dr, synchronize Collectory with GBIF, and update dataset settings

[ ] 1. Go to Collectory's GBIF Synchronization section.
[ ] 2. Click on 'Delete from GBIF.'
[ ] 3. Untick the 'is shareable with GBIF' option.
[ ] 4. Ensure the GBIF registry key is retained.
[ ] 5. Set the dataset to private.
[ ] 6. Add details to the Notes field to indicate this has been "deleted"

### Task: Execute Delete_dataset_dag in AWS Managed Apache Airflow

**Description:** Execute the 'Delete_dataset_dag' in AWS Managed Apache Airflow with specific parameters to perform a soft delete of the Data Repository (DR)

[ ] 1. Navigate to AWS Managed Apache Airflow.
[ ] 2. Execute the "Delete_dataset_dag" with the following parameters:

   - "datasetIds": drXXXX, drXXX, drXXXX
   - "remove_records_in_solr": true
   - "remove_records_in_es": false
   - "delete_avro_files": true
   - "retain_dwca": false
   - "retain_uuid": true

[ ] 3. Remove the DwCA from the dwca-imports bucket

**Note:** 1. _The "Delete from GBIF" button in Collectory won't appear if the license on the data isn't compatible with GBIF. You can quickly edit the license and then the delete button will come back, and then you can use it.
2. Soft delete means that we have removed the Avro files while retaining the UUIDs and the collectory records. (These datasets will not be included in the next index run)_



- [ ] After creation, add this issue to the Data Management project board https://github.com/orgs/AtlasOfLivingAustralia/projects/9

