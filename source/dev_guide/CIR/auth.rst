================================
Authentication and Permissioning
================================


Authentication
--------------
Authentication uses Django default User/Group model but extends it with UserProfile and Team profile to add additional fields

Permissioning
-------------

"Role" model categorizes permissions of different content types into a bucket. 
Name of Roles are derived from ITIL Standards.

Role uses RASCI Matrix to classify different categories of permissions.

RASCI Matrix (Reponsibility Assignment Matrix).
-----------------------------------------------
* 'R','Responsible - Those who do the work to achieve a task.'),
* 'A','Accountable - The one ultimately answerable for the correct and thorough completion of task (Approver)'),
* 'S','Support - Resources allocated to responsible and help complete the task.'),
* 'C','Consulted - Those whose opinions are sought, typically subject matter experts.'),
* 'I','Informed - Those who are kept up-to-date on progress.'))

Refer: https://en.wikipedia.org/wiki/Responsibility_assignment_matrix, http://en.it-processmaps.com/products/itil-raci-matrix.html


Another categorization of permissions are based on ITIL Roles Category

ITIL ROLE States
----------------

Refer: http:wiki-en.it-processmaps.com/index.php/ITIL_Roles
 

* 'Service Strategy
* 'Service Design'
* 'Service Transition'
* 'Service Operation'
* 'Continual Service Improvement'
* 'Non IT'


"TeamResponsibility" model ties roles back to groups and manages permissions assigned for team to a content type via a Role.  

Note: Permissions are eventually tied back to Django "Group" model and content-type via Django-Guardian battery. 
Hence any model can easily ready back permissions assigned without hassle of going through roles. Roles are only used for ease of classification and assignment of permsssions to teams/users.





