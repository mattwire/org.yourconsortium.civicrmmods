# org.yourconsortium.civicrmmods

Overrides to Core CiviCRM.  Currently overrides CRM/Case/BAO/CaseContact.php to workaround an issue in 4.7.27 which doesn't allow updating an existing case.

The workaround is to call the API function CaseContact.getsingle in CRM_Case_BAO_CaseContact::create and update the CaseContact ID if it exists.  This is probably caused the the change to a unique index on the case_contact table. 