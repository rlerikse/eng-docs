
# GitHub Teams

## Introduction
GitHub Teams is a feature that allows you to group people together to collaborate on projects. 
This feature is useful for managing permissions and access to repositories. 
In this guide, we will show you how to create GitHub Teams.

## Prerequisite
- GHEC GitHub account
  - If you don't have a GHEC GitHub account, please find the steps to request access here [organization GitHub GHEC request access](https://github-guide.company.com/ch01/04-request-access.html)
  - Once access is provisioned, you can find the next steps to login to GHEC GitHub account [organization GitHub GHEC login](https://github-guide.company.com/ch01/05-login.html)

## Steps to create Github Teams
1. Decide on the team name and description. 
   - We recommend following guidelines for naming the team:
     - Use `<EAMS acronym>` & `<EAMS ID>` in the team name to identify the team as part of EAMS.
     - Use `<Department Name>` in the team name to identify the team as part of the department.
     - Use `<Skill Team Name>` in the team name to identify the team as part of the skill team within department.
     - At last, you can designate `<Role>` of the team members in the team name.
     - for example, 
     `<EAMS acronym>-<EAMS AppID>-<Department Name><Skill Team Name>-<Role>` -> `t3cu-53996-ftp-aiml-admins`
   - We recommend following guidelines for Roles:
      - name role `admins` for the team members who will have full access to the repository.
      - name role `developers` for the team members who will have read/write access to the repository.
      - name role `code-owners` for the team members who will be responsible for the code review and approval.
        - there are some special steps you need to take to assign `code-owners` team in the repository, please refer to the [Assigning code owners](#assigning-code-owners) section.
      - as most of our repos will land in `organization-innersource` organization, there exists no need to create `viewer` role as by default all `F` and `A` employees have read access to all repos in this org.

2. Log in to EATM GitHub Teams creation tool using the link [EATM Create Teams](https://eatm.company.com/teamcreation)
<img src="/images/analytics/github migration/login_eatm.png" width="900"/>
3. `organization-innersource` organization is by default selected in the tool
4. Put name of your team in the `Team Name` field **_Note:_** :memo: please put the team name as skill name for making it change agnostic e.g. aiml -> team for AIML work etc.
<img src="/images/analytics/github migration/eatm_add_team_name.png" width="900"/>
5. Assign at least two CDSIDs in the maintainers field, they will have the admin access to the team.
<img src="/images/analytics/github migration/eatm_assign_two_cdsids.png" width="900"/>
6. Click on create button
7. You will see a success message with the team name
<img src="/images/analytics/github migration/eatm_team_creation_success_msg.png" width="900"/>
8. You can verify the team creation by going to the [Organization Inner Source Team Page](https://github.com/orgs/organization-innersource/teams)

## Steps to add members to the team
1. Go to the [Organization Inner Source Team Page](https://github.com/orgs/organization-innersource/teams)
2. Search by team name in the search bar to find the team
<img src="/images/analytics/github migration/github_search_team_name.png" width="900"/>
3. Click on the team name and then click on `Add a member` button
<img src="/images/analytics/github migration/github_add_team_member.png" width="900"/>
4. Enter the CDSID of the member you want to add to the team and click on the `Add` button
<img src="/images/analytics/github migration/github_add_cdsid_member.png" width="900"/>
6. You can see the member added to the team
<img src="/images/analytics/github migration/github_member_added_to_team.png" width="900"/>

## Assigning code owners

### Step1: Enable branch protection on the repository

1. Go to the repository where you want to assign the code owners
2. Click on the `Settings` tab
3. Click on the `Branches` tab
4. Click on the `Add branch protection rule` button
<img src="/images/analytics/github migration/github_add_branch_protection_button.png" width="900"/>
5. Edit branch protection rule like below:
    - Enter the branch name in the `Branch name pattern` field
    - Check the `Require pull request reviews before merging` checkbox
    - Check the `Require approvals` checkbox, modify the number of approvals as per your requirement
    - Check the `Require review from Code Owners` checkbox
    - Make sure to check `Do not allow bypassing the above settings` checkbox
    **_Note:_** :memo: you can add custom rules as per your requirement.
    - Click on the `Save changes` button
<img src="/images/analytics/github migration/branch_protection_rule.png" width="900"/>
6. Now you have branch protection on `main` branch

### Step2: Assign Code Owners team to the repository
1. Go to the repository where you want to assign the code owners
2. Click on the `Settings` tab
3. Click on the `Access` tab
4. Click on the `Teams` tab
5. Click on the `Add a team` button
6. Search for the code owners team and click on the `Add team` button
<img src="/images/analytics/github migration/github_add_code_owner_team.png" width="900"/>
7. Assign write permissions to the code owners team
<img src="/images/analytics/github migration/assign_write_permission_to_code_owners_team.png" width="900"/>
8. Now the code owners team will be responsible for the code review and approval

### Step3: Add `CODEOWNERS` file to the repository
1. Go to the repository where you want to assign the code owners
2. Click on the `Add file` button
3. Click on the `Create new file` button
4. Enter the file name as `CODEOWNERS`
5. Add the code owners team name in the file
<img src="/images/analytics/github migration/create_code_owner_file.png" width="900"/>
6. Click on the `Commit new file` button and merge to branch
7. Now the code owners team will be responsible for the code review and approval

## Important Links:
- [organization GitHub EATM Tool](https://eatm.company.com/home)
- [organization GitHub Migration WebEx Space (Self-Join) Link](https://www.webexteams.company.com/space?r=zi3o)
