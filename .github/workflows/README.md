# Populate Workflows Action

This repository contains a composite GitHub Action and a workflow to populate workflows in multiple target repositories from the same organization. It is intended to be used as a GitHub Action in a repository to copy all the workflow files from a directory to multiple target repositories. These target repositories are specified in a file named `target-repos.txt` in the repository where the action is ran. The workflow files to be copied should be stored in the `.github/workflows/my-workflows` directory of the repository where the action is ran. 

## Requirements

- **Personal Access Token (PAT)**: A GitHub token with `repo` scope to push changes to the target repositories. Store this token as a secret named `MY_TOKEN`.
- **File**: A file named `target-repos.txt` containing the list of target repositories (one per line) in the format `repo-name`.
- **Workflows**: The workflow files to be copied should be stored in the `.github/workflows/my-workflows` directory of the repository where the action is ran.
- **Target Repositories**: The target repositories should be in the same organization as the repository where the action is ran, and have the `.github/workflows` directory.
  
## File Structure

```plaintext    
    .
    ├── .github
    │   └── workflows
    │       └── populate-workflows.yml
    │       └── my-workflows
    │           └── workflow-to-be-copied.yml
    │   └── actions
    │       └── populate-workflows
    │           └── action.yml
    ├── .gitignore
    ├── README.md
    ├── target-repos.txt
```

