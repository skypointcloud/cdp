# Security
This section is one of the key features for any platform as it ensures a secure and safe environment to work on data that is sensitive in all aspects. To provide security, there are certain roles defined to ensure that every user gets access to only those sections of the platform which they actually require preventing unncessary access to anyone.

## Security Roles
On our platform, we have divided Roles into 4 categories:
1. Viewer: Permission to view an instance.
2. Contributor: Permission to contribute to the platform post admin permissions.
3. Instance Admin: Permission to view, edit and manage current instance.
4. Tenant Admin: Permission to view, edit and manage current tenant and all of its instances. 

### Permissive actions for a Viewer
1. Explore insight on the Home Page.

2. Within the Data section of the platform, a viewer can:
    - View the Dataflows that are established within your tenant and instance, including the state and the latest update.
    - View and filter data Entities.
    - View and explore data mapping and criteria associated with the map and match steps within Stitch process.
    - Explore data entities that will display in customer profiles in the Timelines.
    - Review data Associations for your source and target entities.

3. Within the Privacy section of the platform, a viewer can:
    - View your Data and PII Maps
    - Search and filter established Data Process Activities and view your Consent Flags.
    - Search and filter the Data Subject Request queue and review the Run History.

4. Search and filter customer profiles using the Profiles page.

5. View and explore Profile Details including Customer Profiles, Timeline, and Metrics.

6. Explore and export entities using the Entities page.

7. View the status of system processes using the System page.

8. Export Audiences from the **Actions** > **Export** page to either a *.CSV file* or to an Export destination.

### Permissive Actions for a Contributor
1. All permissions available to the Viewer.
2. Load and transform data using the Data sources page.
3. Complete the Data Unification sections (Map, Match, and Merge) which result in the unified customer profile entity.
4. Define Relationships and Activities.
5. Create Audiences using the Insights > Audiences page.
6. Create metrics using the Action > Metrics page.
7. Manage configuration and enrich customer profiles from the Enrichment page (for first party enrichments only).

### Permissive Actions for Administrator

1. All permissions available to the Contributor.
2. Change settings on the **Settings** > **Platform**, including the working language and refresh schedules for your system processes.
3. View and add users and specify roles using the Security page.
4. Set up and Configure Audience destinations using the Export destinations page.
5. Add and use the Power Apps connector to create apps with SkyPoint Cloud data.

**Note**

1. Permissions availed to the tenant administrator are only limited to the particular tenant and all of its instances.
2. Permissions availed to the instance administrator are only limited to a particular instance and **not to** any other instances present in the same tenant.

## Tabular Representation of All Users with Roles
All the users associated on this platform have an entry in this table with their details regarding certain roles assigned to them. Every row corresponds to a single user and every column has some specific entity related to that user. Some important column attributes are:
1. Name: Name of the user with the email address.
2. Source: Account which was used for Login
3. Type: Default is *User*.
4. Role: The assigned role to that particular user.
5. Status: *Active* if the user is currently a part of the tenant and *Inactive* if the user is currently blocked for the tenant.
6. Multi-Tenant: *Yes* if the user is currently given access to more than one tenant and *No* if the user is currently given access to only one tenant.
7. Action: This is an option when you want to quickly delete, unlink or block a user. To perform any of the three actions, click on the 3 dot icon and select the action you want to perform.

## Tabular Repersentaion of All Invited Users and their Acceptance Status
When a user is invited on this platform with certain roles assigned to him/her, a track record gets feed on into this table with certarin attributes for every user details. Some of the details are:
1. Email: Email address of the user who got invited.
2. Role: The designated role assigned to the user.
3. Send Date: The date and time on which the invitation request was sent.
4. Resend Date: The date and time on which the invitation request was resent.
5. Status: *Accepted* if the user accepted the invitation, *Pending* if the user's has not yet accepted the invitation and *Expired* if the user was not able to accept the invitation whthin 24hrs.
6. Accepted Date: The date and time when the invitation was accepted.
7. Invited By: The designated person who invited the user.
8. Action: If, for some reasons the user was not able to accept the invitation within 24hrs, the platform provides a  feature where you can resend the invitation just by clicking on the 3 dot icon below the action column.

## Steps to Create a new User
1. Navigate to **Settings** > **Security** where you will see all the users with their assigned roles in a tabular form.
2. Click on *Create Users* written on top of the page. A small window will pop up on top of the page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/createuser.PNG?raw=true)

3. Select the role which you want to assign the user.
4. Fill all the details of the user under the specific fields and click on Save.

## Steps to Invite a User
1. Navigate to **Settings** > **Security** where you will see all the users with their assigned roles in a tabular form.
2. Click on *Invite Users* written on top of the page. A small window will pop up on the right side of the page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/inviteuser.PNG?raw=true)

3. Select the type of role you want to assign. You will see the various roles listed in the dropdown menu.
4. Fill in the email ids for the users whom you want to invite and assign the particular role.
5. Click on **Save** to complete the assignment process. The user will be assigned with that particular role and the entry will be made in the details table.

## Steps to Assign a Role to a user
1. Navigate to **Settings** > **Security** where you will see all the users with their assigned roles in a tabular form.
2. Click on *Assign Roles* written on top of the page. A small window will pop up on the right side of the page.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/assignrole.PNG?raw=true)

3. Select the type of role you want to assign. You will see the various roles listed in the dropdown menu.
4. Search for the user whom you want to assign the particular role.
5. Click on **Save** to complete the assignment process. The user will be assigned with that particular role and the entry will be made in the details table.

## Steps to Unlink User
1. Navigate to **Settings** > **Security** where you will see all the users with their assigned roles in a tabular form.
2. Click on the checkbox on the side of the user which you want to unlink.
3. You will see that the *Unlink users* button on top of the page will be enabled. Click on it to unlink the user/s.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/unlinkuser.jpg?raw=true)


## Steps to Delete User
1. Navigate to **Settings** > **Security** where you will see all the users with their assigned roles in a tabular form.
2. Click on the checkbox on the side of the user which you want to delete.
3. You will see that the *Delete users* button on top of the page will be enabled. Click on it to delete the user/s.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/deleteuser.jpg?raw=true)