<!-- u251002 -->

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
