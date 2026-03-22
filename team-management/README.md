# Team Management

This section covers how the Full Metal Falcons organize code, manage access, and onboard new members using GitHub.

## New Members

If you're new to programming and Git, start with the [beginners](https://github.com/FullMetalFalcons/beginners) repository for tutorials on getting started with GitHub and making proper contributions.

Then follow the [Getting Started](../getting-started/README.md) guide to set up your development environment.

## GitHub Organization Structure

The team uses GitHub's **organization and teams** features to manage access control. This ensures that only authorized members can push code to specific repositories, and all changes are tracked.

Reference: GitHub docs on [adding members to a team](https://help.github.com/articles/adding-organization-members-to-a-team/) and [team management](https://help.github.com/articles/about-teams/).

### Teams

| Team | Role | Permissions |
|------|------|-------------|
| **Students** | All student members | Read/Write on assigned repos |
| **Mentors** | All mentors | Admin on all repos |

> **Important:** Every organization member must be added to at least one team immediately upon joining. Members not assigned to any team may experience unexpected permission behavior.

## Repository Setup

### Adding Teams as Collaborators

When creating or modifying a repository, immediately configure team access:

1. Open the repository and click **Settings** (gear icon)
2. Click **Collaborators & Teams**
3. Use the **Add a team** dropdown to add each relevant team
4. Set permission levels:
   - **Students** working on the repo → **Write**
   - **Mentors** → **Admin** (always, on all repos)
5. Settings auto-save when the green checkmark appears

> **Note:** No one can read, write, or modify a repository except the creator until permissions are set. Do this immediately after creating the repository.

### Branch Protection Rules

Branch protection adds an additional layer of access control, restricting who can push directly to critical branches (e.g., `main`):

1. Go to repository **Settings → Branches**
2. Click **Add rule**
3. In **Branch name pattern**, enter `main` (or `master`)
4. Check **Restrict who can push to matching branches**
5. Type the team name that should have push access (should match the team with Write access)
6. Select the matching `organization/team` from the dropdown
7. Click **Create**

## Season Repository Convention

Each season, create a new repository for each sub-team's robot code. Use a consistent naming convention (e.g., a season prefix or team identifier) so repositories are easy to find in the organization.

## Related Topics

- [Getting Started](../getting-started/README.md) — new member onboarding and dev environment setup
- [Programming](../programming/README.md) — the code that lives in these repositories
