# Contributing

## Prerequisites

- To be able to contribute to the repo you will need to install the power platform cli tool. You can find information on how to install this here [Power Platform CLI](https://learn.microsoft.com/en-us/power-platform/developer/cli/introduction). 

- Same Prerequisites detailed on the README applies. Before importing or exporting the solution ensure variable names and collection names created are unique.

- To gain a better undertsanding of how the repo manages files for the canvas app within the solution you can take a look at [Source code files for canvas apps](https://powerapps.microsoft.com/en-us/blog/source-code-files-for-canvas-apps/)

## Importing

- You will need to import the solution as described in the [README](README.md), if this is your first time.

- Otherwise take the following steps in updating your solution.

- Pull the latest changes from master.

- If you would like to retain any changes done on the solution in your environment. First follow the export guide, skipping the pull request step. This should merge the changes from master with your changes. Then follow the remainder of the import guide.

- Pack the solution file using power platform cli, as shown in the code snippet.

```
pac solution pack --zipfile desired-zip-file-name --folder path-to-repo/ReviewHubDev -ad -aw -c -pca -p Unmanaged
```

- Import the generated zip file into your environment.

## Exporting

- When done with your changes within the solution. Change the solution version to match the date you open your PR and then publish all customizations.

- Export the solution as unmanaged, and download the zip file.

- Checkout from master to a new branch within your local repo.

- Extract the zip file using the power apps cli to unpack the solution, as shown in the code snippet.

```
pac solution unpack --zipfile path-to-exported-zip-file --folder path-to-repo/ReviewHubDev -ad -aw -c -pca -p Unmanaged
```

- Once done commit your changes and create a pull request.