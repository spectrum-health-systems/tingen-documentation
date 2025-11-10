<!-- u251106 -->

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)

<div align="center">

  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-dark-400x63.png">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
    <img alt="Fallback image description" src="https://github.com/spectrum-health-systems/tingen-projects/blob/main/logos/tngndocs-light-400x63.png">
  </picture>
  <h1>
    Testing: OpenIncident Module
  </h1>

</div>

> Last updated: November 8, 2025

# Testing Open Incident form functionality




All testing is done while logged into Avatar as the "TESTUSER" user.

REMVOE CONFIG


## The ***Program of Incident*** field

Staff should not be able to submit a new incident without choosing a value for the **Program of Incident** field.

Currently the title of the field is red, but is not technically required.

### Expected outcome

The web service should display a message informing the user they cannot submit the form until the *Program of Incident* field is completed.

### Testing procedure

1. Opened the `Open Incident` form

2. Typed "40" in the search bar

3. Clicked the `New Incident` button

A new, blank Open Incident form opened.

4. Completed the following required fields:

* Brief Incident Description:
* Date Incident Occured
* Date Incident Reported
* Time Completed
 
5. Clicked the `Submit` button

The "Program of Incident is not valid" message appears.

6. Completed the *Program of Incident* field

7. Clicked the `Submit` button

The incident was submitted, and the form closed.

## The original author opens an incident

Staff should be able to open any incidents they are the original creators of.

### Expected outcome

Nothing should happen!

### Testing procedure

1. Opened the previously created incident

The incident opened as expected.

2. Added text to the Incident Description

3. Clicked the `Submit` button

The incident was submitted, and the form closed.

## Opening an incident created by another user

Only staff that are members of the authorized list of Avatar User Roles should be able to open incident reports they have not created, but cannot save any changes they make.

Staff that are not members of the authorized list of Avatar User Roles cannot open incidents they did not create.

### Expected outcomes

When opening an incident report they did not create, authorized staff members should receive a message letting them know any changes they make will not be saved. If the user attempts to submit changes,they will receive a message letting them know they are not able to submit the form.

Unauthorized staff members should not be able to open any incident report they did not create.

### Testing procedures

1. Verified the TESTUSER account does not have an authorized user role.

2. Opened an Open Incident report created by another user.

Received the "You are not authorized to view" message, and sent to the home screen.

3. Add the TESTUSER user role to the OpenIncident.config file

4. Opened an Open Incident report created by another user.

Received the "Not original author" message, and the form opens.

5. Click the Submit button

Received the "Can't submit" message, and returned to the form.
















## Verify the `_VerifyOriginalAuthorIsOpening` command

- [ ] Login as USER1
- [ ] Create a new Open Incident "USER1_testing"
- [ ] Submit "USER1_testing"
- [ ] Open "USER1_testing"
- [ ] Add a note to the Incident Description field
- [ ] Submit the form
- [ ] Logout of USER1

## Verify the translation table is working

- [ ] Copy "USERID_User Description_{AvatarSystem}.txt" to "USERID_User Description_{AvatarSystem}_backup.txt")
- [ ] Open ""USERID_User Description_{AvatarSystem}.txt"
- [ ] Remove USER2 from the file
- [ ] Save the modified file
- [ ] Login as USER2
- [ ] Attempt to open "USER1_testing" - you should receive the "Your use cannot be found" message, and the form should close
- [ ] Delete the ""USERID_User Description_{AvatarSystem}.txt" file
- [ ] Rename "USERID_User Description_{AvatarSystem}_backup.txt" to "USERID_User Description_{AvatarSystem}.txt"

## Verify the `_VerifyOriginalAuthorIsSubmitting` command

- [ ] Attempt to open "USER1_testing" - you should receive the "You are not the original author" message, and the form should open
- [ ] Verify you can view the incident
- [ ] Add a note to the Incident Description field
- [ ] Attempt to submit - you should receive the "You can't submit" message
- [ ] Discard the form form
- [ ] Logout of USER2

## Verify USER2 changes were not submitted

- [ ] Log in "USER1"
- [ ] Open "USER1_testing"
- [ ] Confirm the modification by USER2 was not saved

***

[[🏠︎](../../README.md)] ❬ [Static documentation](../README.md) ❬ [Diagrams](README.md)
