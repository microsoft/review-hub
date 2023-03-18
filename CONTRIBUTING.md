# Contributing

## Prerequisites

- To be able to contribute to the repo you will need to install the power platform cli tool. You can find information on how to install this here [Power Platform CLI](https://learn.microsoft.com/en-us/power-platform/developer/cli/introduction). 

- Same Prerequisites detailed on the README applies. Before importing or exporting the solution ensure variable names and collection names created are unique.

- To gain a better undertsanding of how the repo manages files for the canvas app within the solution you can take a look at [Source code files for canvas apps](https://powerapps.microsoft.com/en-us/blog/source-code-files-for-canvas-apps/)

## Importing

- You will need to import the solution as described in the [README](README.md), if this is your first time.

- Otherwise take the following steps in updating your solution.

- Pull the latest changes from main.

- If you would like to retain any changes done on the solution in your environment. First follow the export guide, skipping the pull request step. This should merge the changes from main with your changes. Then follow the remainder of the import guide.

- Pack the solution file using power platform cli, as shown in the code snippet.

```
pac solution pack --zipfile desired-zip-file-name --folder path-to-repo/ReviewHubDev -ad -aw -c -pca -p Unmanaged
```

- Import the generated zip file into your environment.

## Exporting

- When done with your changes within the solution. Change the solution version to match the date you open your PR and then publish all customizations.

- Export the solution as unmanaged, and download the zip file.

- Checkout from main to a new branch within your local repo.

- Extract the zip file using the power apps cli to unpack the solution, as shown in the code snippet.

```
pac solution unpack --zipfile path-to-exported-zip-file --folder path-to-repo/ReviewHubDev -ad -aw -c -pca -p Unmanaged
```

- Once done commit your changes and create a pull request.

## Branch Permission Guidelines
The following guidelines describe the branch permissions for contributing to this project:

### Main Branch
The main branch (usually named "main" or "master") is the primary branch for this project. It should always reflect a stable state of the project and only trusted collaborators should have write access to this branch.
- Only trusted collaborators have write access to the main branch.
- Pull requests into the main branch must be reviewed and approved by at least one trusted collaborator.
- Pull requests into the main branch must pass all status checks, including automated tests, code formatting checks, and any other checks required by the project.

### Feature Branches
Feature branches are used for developing new features or making changes to existing code. They are created from the main branch and are intended to be temporary.
- Contributors are allowed to create and push changes to their own feature branches.
- Pull requests from feature branches must be reviewed and approved by at least one trusted collaborator before they can be merged into the main branch.
- Pull requests from feature branches must pass all status checks before they can be merged.

### Code Reviews
Code reviews help ensure that changes are high quality and aligned with the project's goals.
- Pull requests must be reviewed and approved by at least one trusted collaborator before they can be merged.
- Pull requests must be reviewed by a code owner (i.e. a trusted collaborator who is responsible for maintaining the affected code) before they can be merged.

### Write Access
Write access to the repository is granted selectively to trusted collaborators who have a proven track record of contributing positively to the project.
- Only trusted collaborators are granted write access to the repository.
- The "collaborators" permission level is used for trusted collaborators.

### Status Checks
Status checks help ensure that changes meet the project's standards and requirements.
- Status checks must pass before pull requests can be merged.
- Status checks include automated tests, code formatting checks, and any other checks required by the project.

### Protected Branches
Protected branches prevent unauthorized changes to important branches in the repository.
- Important branches, such as the main branch and release branches, are protected.
- Only trusted collaborators can push changes to protected branches.

### Documentation
These guidelines are documented in the CONTRIBUTING.md file, which should be read by all contributors before submitting changes to the repository.