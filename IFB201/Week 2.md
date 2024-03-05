#Week 2
The first tutorial of the semester comprised of 2 modules.

Both modules serve the intent of getting you acquainted with the salesforce environemnt

## Module 1
In this module, we open up with learning about setting up currencies and modifying our "Company's" information. They can both be found under:
```Setup < Search "Company Information" < Edit```


In tandem with setting up currencies we can also edit the exchange rate of them, this is found by:
```Setup < Search "Manage Currencies"```


Something that was also touched on was the oppurtunities function, which I am not quite sure how we are to use it outside of testing it for currency, regardless its found by:
```App Launcher < Sales < Oppurtunities```

Chatter groups for your organistion was also touched on:
```App Launcher < Groups```
These are like little forums that you can set up for specific groups and teams, alongside setting specific access conditions.

that is basically it. asife from a few other things.

## Module 2
First up is restricting login hours and restricting login IP ranges, both found under:
```Setup < Profiles```
here you can find the "login hours" heading, where we can limit the timeframe that people cna log in. Under the same area you can find the Login IP Ranges, where you can set certain IP ranges that are acceptable for connections. In profiles we can also create new profiles, pretty self explanatory tbh

Under ```Setup < Permission Sets``` we can create, well, permissions for our users, giving or removing the ability for users to do certian things, in the case of the tutorial we created a Delete Accounts permission, giving people apart of the Salesforce Platform license the ability to delete accounts. After creating the permission we need to actually give those permissions to the set. this is by clicking Object Settings in the Apps section. Then pressing Accounts, editing that page we select Read, Edit and Delete under Object Permissions. To give people this permission sets, select Manage Assignments while still on the Accounts page.

Logging in as other Users is very useful when wanting to test if your permission sets are actually working. This is done through ```Setup < Users```. Navigate to the action column and selecting LOGIN on the person that you wish to log in as, if you cannot log in consider that they are not active or they are just some random shit that you didnt put in to begin with


Creating Custom objects and setting Organization-Wide defaults allows us to create objects and sort people into them.
```setup < object manager```
lets say we wanted to make an object for apllicants
we would start with hitting the create button, custom objeect and then filling out our form appropriately.

We set up a few different objects. Those being Applicant, Interviewer and Position. We are going into a bith more depth on the Position object, by opening the Position object and selecting fields and relationships clicking new and choosing picklist as a data type. This is so that we can create a few new fiels, those being "new" "open" and "closed", making sure to select the restrick box

We also need to set the access mode of the new objects, think like public vs private fields in programming :D

go to ```setup < sharing centre < edit```

Creating a role hiearchy is importnat to understand how your organization is structured. go to
```setup < roles < set up roles < expand all < add role``` complete all the checkboxes, and save

now that we have set up the roles we have to populate them. under the same Roles tab, in the same set up roles tab we press expand all and next to the roles will be an assign button, hwich is what we use.

The second last thing we learned was that of creating sharing rules
navigate back to sharing settings, and in our case we are going to select the Oppurtunites object, we create a new sharing rule named "Share Won Oppurtunities with Account Receivable" fill out the form with the rule type, criterias and who to share it with + access level.

we do similair things with sharing applicants, interviewers and positions between the recruiters, selecting based on record owner, owned by recruiter, shared by recruiter and giving them read only access level

also in this section we learn how create public sharing groups, in this case for all of the VPs
```setup < public groups < new < label VPs < etc```

final thing we learned was setting up account teams
```setup < account teams < enable account teams < add to user's...```
click team roles and click new, enter your stuff and press save

we also created a default account tema to give access
```click own icon < settings < advanced user details < default account team list < add < use search functoin to do a few things``` etc