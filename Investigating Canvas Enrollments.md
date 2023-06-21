- We tie Canvas Enrollments to Sections in Catalog
- if no section id is given, it will use the default section
- canvas enrollment will try to reuse enrollments before
- there is a flag `allow_multiple_enrollments` 
- deleting enrollment is actually the destroy method, workflow_state = deleted

enrollment state -> https://github.com/instructure/canvas-lms/blob/master/app/models/enrollment_state.rb

enrollment state is basically a cache, was created for optimizing
it mostly used for permissions, recalculated every 5 min