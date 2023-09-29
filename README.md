
# Migration Guide: Azure DevOps to GitHub

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

  - [Prepare to Migrate](#prepare-to-migrate)
    - [Alternative Migration Option:](#alternative-migration-option)
  - [Import Organization and Repositories to GitHub](#import-organization-and-repositories-to-github)
  - [Migrate Members](#migrate-members)
  - [Migrate Boards](#migrate-boards)
  - [Migrate Pull Requests](#migrate-pull-requests)
  - [Migrate Additional Data](#migrate-additional-data)
  - [Additional Considerations:](#additional-considerations)
  - [Post-migration Steps:](#post-migration-steps)
- [Additional References:](#additional-references)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Pre-Migration Steps

**[Plan your migration](https://docs.github.com/en/migrations/using-github-enterprise-importer/understanding-github-enterprise-importer/migrating-from-azure-devops-with-github-enterprise-importer#planning-your-migration)** beforehand to ensure a smooth transition with the following steps, which will use the [GitHub Enterprise Importer](https://docs.github.com/en/migrations/using-github-enterprise-importer/understanding-github-enterprise-importer/about-github-enterprise-importer) tool to migrate your data.

- **Warn the team**: Notify your team of the upcoming migration.
 
- **Backup data**: Ensure you have a backup of all data fron the Azure DevOps.

- **[Migration type](https://docs.github.com/en/github-ae@latest/migrations/overview/planning-your-migration-to-github#about-migration-types)**: Determine the type of migration you will perform.

- **[Define Inventory](https://docs.github.com/en/github-ae@latest/migrations/overview/planning-your-migration-to-github#building-a-basic-inventory-of-the-repositories-you-want-to-migrate)**: Define what data needs to be migrated ( users, repos, boards, PRs,  etc. ).

- **[Measure repos](https://docs.github.com/en/migrations/using-github-enterprise-importer/migrating-repositories-with-github-enterprise-importer/migrating-repositories-from-azure-devops-to-github-enterprise-cloud#about-repository-migrations-with-github-enterprise-importer)**: Review the size of your repos to ensure they are within the GitHub limits.

- **[Measure total data](https://github.com/github/gh-migration-analyzer)**: Gauge how much data will be migrated without having to do a dry run migration.

- **[Organization structure](https://docs.github.com/en/migrations/using-github-enterprise-importer/understanding-github-enterprise-importer/migrating-from-azure-devops-with-github-enterprise-importer#what-organizational-structure-do-we-want-in-github)**: Determine how organizations will relate to ADO projects.

-  **[Disaster Recovery]()**: Evaluate Disaster Scenarios and have a backup/rollback plan for issues that may arise during the migration. For example:
   - What happens if the migration fails? Read [Locked repositories](https://docs.github.com/en/migrations/overview/about-locked-repositories#repositories-locked-by-github-enterprise-importer).
   - Security issues ( secrets exposed, public repositories, usage of insecure public libraries. )
   - Pipelines automatically running right after migration and differently from expected.

- **Setup GitHub**: Create a GitHub organization as defined previously.

- **Setup user accounts**: Ensure all users have GitHub accounts.

- **Verify Permissions**: Create a [**PAT**](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops) with the required permissions both in ADO and GitHub. 

- **[Dry-run migration](https://docs.github.com/en/migrations/using-github-enterprise-importer/understanding-github-enterprise-importer/migrating-from-azure-devops-with-github-enterprise-importer#running-your-migrations)**: Perform an automated test migration with [GitHub CLI extensions](https://docs.github.com/en/migrations/using-github-enterprise-importer/migrating-repositories-with-github-enterprise-importer/migrating-repositories-from-azure-devops-to-github-enterprise-cloud) and make sure to [**review the logs**](https://docs.github.com/en/migrations/using-github-enterprise-importer/completing-your-migration-with-github-enterprise-importer/accessing-your-migration-logs-for-github-enterprise-importer) for any errors.

### Alternative Migration Option:
- [GitHub's Expert Services team or a GitHub Partner](https://github.com/services/migrations): Check if your subscription includes migration services.

# Migrating the Inventory

## Import Organization and Repositories to GitHub

## Migrate Members

## Migrate Boards

## Migrate Pull Requests

## Migrate Additional Data
- **Complete Data Migration**: This involves manually transferring any additional data like logs, events, service connections, etc., not covered in the previous steps.

## Additional Considerations:

You can use either the GitHub CLI and API to run your migration. 

While some steps can be automated, a significant portion of the process may need to be manual due to differences between Azure DevOps and GitHub. Advanced customers can use the API to build their own integrations with GitHub Enterprise Importer. 

Refer to the [importer limitations](https://docs.github.com/en/migrations/using-github-enterprise-importer/understanding-github-enterprise-importer/about-github-enterprise-importer#support-limitations-for-github-enterprise-importer) for more information and for further guidance, review the official [GitHub documentation](https://docs.github.com/en/migrations/using-github-enterprise-importer/migrating-repositories-with-github-enterprise-importer/migrating-repositories-from-azure-devops-to-github-enterprise-cloud#about-repository-migrations-with-github-enterprise-importer) and community forums.

## Post-migration Steps:
- **Data Verification**: Match all data (repos, boards, members, pull requests, etc.) against the original inventory.
- **Update Internal References**: Adjust any references from Azure DevOps to GitHub within internal documents such as wiki pages, repositories README.md files, etc.
- **Decommission Azure DevOps**: Once satisfied, back up one last time and then deactivate your Azure DevOps account.

# References:

This guild was build based on the following references:
 
- [GitHub Migrations Documentation](https://docs.github.com/en/migrations)
- [Creating an Issue from Code](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue#creating-an-issue-from-code)
- [Using the Built-in Automations](https://docs.github.com/en/issues/planning-and-tracking-with-projects/automating-your-project/using-the-built-in-automations)
- [GitHub Explore](https://github.com/github/explore)
- [Planning and Tracking Work for Your Team or Project](https://docs.github.com/en/issues/tracking-your-work-with-issues/planning-and-tracking-work-for-your-team-or-project)
- [GitHub Projects as Code](https://www.google.com/search?q=github+projects+as+code&oq=github+projects+as+code+&aqs=chrome..69i57j69i64j69i60.11953j0j7&sourceid=chrome&ie=UTF-8)
- [GitHub Organizations](https://docs.github.com/en/github-ae@latest/organizations/collaborating-with-groups-in-organizations/about-organizations)
