- We are going to check every enrollment if its faulty to detect shard / merge user problesm 


- We cant use the user merge id information, because it seems to be not working and also it does not provide information from back in the day




I would summarize the findings from the last few weeks.
There are two main problems:
* Canvas creates new enrollments for students, when moved to a different section
* There was an issue with Catalog regarding cross shard users


Talking about the intended behaviour first:
In Canvas when you move a student between sections, it actually creates a new enrollment and deletes the other one. 
Catalog tries to follow canvas and it's enrollments as close as possible, so it will create a new enrollment and drop the other one. 
This is intended, and can not be changed currently.

In Canvas the following happens:
1. User is enrolled to Section A -> Enrollment is created (Enrollment A)
2. User is moved to Section B -> Enrollment A is 'deleted', Enrollment B is created
3. User is moved back to Section A -> Enrollment A is undeleted, Enrollment B is deleted
4. User is moved back to Section B -> Enrollment A is deleted, Enrollment B is undeleted.

And back-and-forth.

The issue with Catalog and cross shards: this caused the users to have a wrong canvas user id in catalog, enabling to have multiple ACTIVE enrollments.

From the previous example:
What happened is that we received updates from Canvas, regarding Enrollment A to be dropped, enrollment B to be created.
However due to an issue with shards, enrollment B was created with a wrong canvas user id. This could enable different scenarios of moving, merging etc that resulted in duplicate enrollments.


1.  What is causing some of the students to have a duplicate entry when they are being moved sections (within the same course) via CSV? (and why isn’t it happening to everyone)  
   
   There is an intended and not intended part of this. As described above. There should be two enrollments in Catalog as there are two enrollments in Canvas. However only one should be active.
   
2.  Is there a fix from Catalog’s end to make these numbers more accurate?
   
   We are deploying a fix next week that wont allow to have problems with cross shard users. We are also doing fixing the enrollments retroactievly to have a correct user id.
    
3.  Is there a fix from the clients end which will stop this from happening in upcoming quarters. These students work through a series of 5 courses so we will be running these reports and doing this enrollment process every three months. We are willing to make adjustments to our procedures if it will solve this duplicate problem.
   
   The moving-between-sections is something that is done on canvas and results in multiple enrollments, however only one active.
   
   In New Analytics in the Enrollments tab it can be easily filtered to 'active' and 'completed' enrollments, to only show the relevant fields.