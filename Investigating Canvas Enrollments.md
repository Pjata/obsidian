- We tie Canvas Enrollments to Sections in Catalog
- if no section id is given, it will use the default section
- canvas enrollment will try to reuse enrollments before
- there is a flag `allow_multiple_enrollments` 
- deleting enrollment is actually the destroy method, workflow_state = deleted

enrollment state -> https://github.com/instructure/canvas-lms/blob/master/app/models/enrollment_state.rb

enrollment state is basically a cache, was created for optimizing
it mostly used for permissions, recalculated every 5 min


https://lucid.app/lucidspark/dea95517-51e6-4993-b962-daaab87caff0/edit?beaconFlowId=4F814CDE47C67295&invitationId=inv_bd7ae4e5-fa90-4fc8-89cf-d1572c56d17b&page=0_0#

Course progress:
Module progression is tied to the Canvas User and Course
not sections
