* Check TLS -> we have TLS for Catalog
* We dont have encryption at Rest for Postgres
* Service Review -> needs to have a meeting minutes
* Annual testing of disaster recovery
* Alert for backup failures
- [x] #task Review the items sent by Zsofi 📅 2023-04-03 ✅ 2023-04-03

- http disabled investigate: we have to check if the http transit is either disabled or rerouted to https
- encryption at rest: postgres data has to be encrypted at rest 
- snapshot validation proof: we have to have a proof (yearly) that snapshots can be restored and works
- ping lacework timeline: we have to have a timeline when lacework will be installed, currently dependens on fire team


https://docs.google.com/document/d/1jW9V3VlYSnUpX_WywInvfD7aycD5p6vE015f7LMh9qc/edit#

- [ ] #task Ask fire team to test our monitors for backup failures 📅 2023-05-31