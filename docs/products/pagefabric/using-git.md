# Using Git in PageFabric
Git is a famous source control solution used by millions of organizations around the world.

Note: The following features are not available yet:

* Merging modifications
* Having multiple branches
* Online Git repositories such as GitHub.com, GitLab.com...

## Application settings

Git requires that you specify a user name and an email. By default, PageFabric will fill these details with your current
Windows details. If you want to change them, go to Application Settings > Git.

## Enable Git for your website

To use Git with a PageFabric website, you have to enable the option in the Website settings dialog, then turn on the
Enable Git repository for this website.

## Supported Git features in PageFabric

### Watch files

To enable Git features such as commit, history... you have to Watch files. To watch a file, right click a file in the
Website Explorer, then click File versioning > Watch file. The red tick will appear next to the file, indicating that
the file is watched and has pending changes.

> Note: Watching a file means adding the file to the local Git index.

This figure shows the several status of files in the Website explorer pane:

Description of the different statuses:

| Symbol                                        | Description                                                                                                                                                                                                       |
|-----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Little Red tick (like number 1 on the image)  | This file has pending changes in your folder. You can commit this file to save it to your local warehouse.                                                                                                        |
| Little Blue lock (like number 2 on the image) | This file has not pending changes and is watched by the application. When you edit the file, the lock automatically transforms to a red tick. You can use Git features with this file, such as history, commit... |
| No symbol (like number 3 on the image)        | This file is not watched by the application. You cannot use Git features because it is not present in your local warehouse. You have to use the File versioning > Watch file feature to add it to the Git Index.  |

### Commit changes to local repository

Once you have modified your files, you have to commit them to your local repository. This action is called Commit.

All your pending modifications will be stored in the local repository, and files will be marked as synced.

To commit your changes, follow these steps:

1. In the ribbon, select **Git > Commit**, the Commit dialog opens
1. Type a comment about your changes
1. Include or exclude files to commit to your repository (right click files and select Include or Exclude in the two
   list boxes)
1. Click the **Commit** button to proceed

### Set the remote repository on an existing project

If you want to store your repository on a remote location, you have to add the location in **Git ribbon tab > Add remote
repository link**.

Provide the network location of the remote repository. If network credentials are required, enable the Specify network
credentials option and provide User login and User password.

### Push changes to the remote repository

When you want to share your modifications with the other members of your team, you have to push your modifications to
the remote repository.

Click the Git ribbon tab, then click the Push to remote repository button.

> Note: This operation is the equivalent of the Push force Git command. It will replace the remote files with the latest
> version from your local repository. It is currently not possible to merge files.

### Get changes from the remote repository

When you want to get the modifications made by other members of your team:

Click the Git ribbon tab, then click the Pull from remote repository button.

> Note: This operation is the equivalent of the Pull force Git command. Conflicts will be replaced with the latest
> version from the remote repository. If you have pending modifications on files that are not subject to conflict, your
> modification will remain. It is currently not possible to merge files.

### Show file history

One of the biggest advantages of using Git (or any Source Control solution), apart of collaboration is to be able to
save file history. You can can of course see an old version of your pages, compare the current version to an old one,
and even restore a file if you want.

### Compare file versions

To compare the current version of a page to an older one, follow those steps:

1. Right click the page in the Website explorer pane
1. Select File versioning > Show file history
1. If the selected page has been committed several times in the past, you will see the history of all changes store in
   your local Git warehouse
1. Right click the version you want to compare with the current version, then select Compare

### Restore an old version of a file

To restore the contents of an older version of an existing page:

1. Right click the page in the Website explorer pane
1. Select File versioning > Show file history
1. If the selected page has been committed several times in the past, you will see the history of all changes store in
   your local Git warehouse
1. Right click the version you want to restore with the current version, then select Restore the contents of this state

> Note: This operation will replace the whole file. It means that all the languages of the page will be replaced. It is
> not currently possible to only restore a specific language version of a page.

## Discard pending modifications of file

To restore the contents of an older version of an existing page:

1. Right click the page in the Website explorer pane
1. Select File versioning > Discard pending changes
1. A message box will ask for your confirmation, click the Restore button

> Note: This operation will replace the whole file. It means that all the languages of the page will be replaced. It is
> not currently possible to only restore a specific language version of a page.