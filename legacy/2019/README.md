# Documentation

## New students - beginner setup and tutorials
For anyone interested in coding anything see the [beginners](https://github.com/FullMetalFalcons/beginners) repository for information on getting started with github, and how to make productive and proper contributions to any existing code you have permissions to modify.

## Robot Interaction
For interacting with the robot see the [robot-basics](robot-basics.md) page

## Control System Documentation & Environment Set-Up
For a list of documentation links for the control system and how to set up the environment for development (LabVIEW, etc.) see [2018 important links](important-links.md).

## Mentors - Github Teams for Access Control
For controlling which students have access to which code base (separation of concerns), we utilize built-in github teams.  This allows us to relatively easily manage who can push code to which repositories.  Github docs for [adding members](https://help.github.com/articles/adding-organization-members-to-a-team/) and [general team info](https://help.github.com/articles/about-teams/)
* Ensure all students are at least in the `students` team so proper access control functions are enabled, otherwise weird behavior will happen
* Ensure all mentors are in the `mentor` team

## Mentors - Repository Setup - Adding Teams
When creating/modifying a repository it is imperative that you add teams to the collaborators section under settings.  This separation of concerns ensures only specific students have write access to a particular repository and ensures we can track who modifies things at all times.

Note that new organization members need to immediately be invited into teams once added to the organization.

note that no one can read or write or modify a repository except the creator/owner until the permissions are set, so this should be done immediately after creating the repository
1. open a repository from the main page, or via the repository tab for the organization
2. click the `settings` cog/gear icon
3. click `collaborators & teams`
4. click the dropdown `add a team: *select team*`
5. select each team until all are listed on the main page and the dropdown is no longer visible
6. click each team's dropdown and change from `read` to `write` if that particular sub-group of students requires write permissions to the repo
7. `mentors` should always have `admin` on all repos to allow for modification of everything, etc
8. these settings are saved when the green checkmark is displayed, there is no explicit save button for team permissions

## Mentors - Repository Setup - Adding Branch Commit Rules
Now that you have a repository with team access control configured you can further verify that only those team members that are allowed to, can commit to a specific branch.  This should further prevent anonymous commits, as having teams is the existing access gate on this.

Note that this only works if all students and mentors are actually in a team, if an organization member is not in any teams then unexpected behavior can occur. New organization members need to immediately be invited into teams once added to the organization.

1. click on the `settings` cog/gear icon for a the repository
2. click on the `branches` button on the left side bar
3. click the `add rule` button
4. in the `Apply rule to` section type in `master`
5. check the `Restrict who can push to matching branches` box
6. type in the TEAM name that you want to have commit access, should probably match whoever has `write` access you configured for the repo.  This should then show a dropdown matching the `organization/TEAM`
7. click the auto-populated option and click `create`


## Tutorials
For various tutorials in Java and various libraries/dependencies, see [tutorials](tutorials.md).
