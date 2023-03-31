* We have main 3 products (Catalog, Commons, Payment-Redirector) each follows the same release process
* We have 2 on callers each week: a primary and secondary
  
  Preparation:
  
* The primary's job is to release and monitor, with the help of the secondary
* Each monday the release leadership (PM, EM and the on callers) sits together to discuss the beta and prod release scope
* We use a 'simple' release sheet for each product, for example:
  https://docs.google.com/spreadsheets/d/1P-oF9A73iMOjXdXYWYSM9LtQX2Hwn7VRb1DwkuPZERI/edit#gid=620801242
* The sheet is the single source of truth for everything related to the release
* We create the scope of the beta release 
* Here we discuss potentional risks, actions to do after the deploy and document it in the sheet
* After the release meeting the on caller starts the release(s)
  
  The release:
  
* We have slack channels setup for any new sentry errors and alerts
* The primary's job is to acknowledge every error and alerts, investigate if its due to the release, ask for help if needed
* 