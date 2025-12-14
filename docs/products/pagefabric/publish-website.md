# WebSite publication

When you are ready to push your pages online, you can generate the website using the Publish Website feature.

You can use any FTP client application to send your web pages online.

> Note: The publication process will deploy the files that are generated using the Build website files command. Do not
> forget to build your website files before you publish them in order to always have up to date files.

## Publication settings

Here are the general options available for the publication feature:

| Option               | Description                                                                                                                                                                                                           |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Generate Sitemap.xml | Enable this feature to automatically build the sitemap.xml file when you build the website files. This file is important to help search engines to find your content                                                  |
| Publication mode     | Select the publication location to use: Local folder or FTP server                                                                                                                                                    |
| Target update mode   | Select the update method to perform: Standard will simply copy your website files to the target location; Mirror will make the target the exact copy of the source directory to the target location, use with caution |

> Warning: The Mirror update mode will erase all existing files at the target location before deploying the new ones. If
> you use the Local folder publication mode, the folder will be deleted and recreated. DO NOT select a folder that
> contains import files.

## Local folder publication

Local folder publication lets you publish all your files to a local directory or any network drive.

To configure this mode:

1. Fill the Target folder field
1. Click Save
1. Click the Publish website ribbon button in the Website tab

## FTP publication

Local folder publication lets you publish all your files to a local directory or any network drive.

To configure this mode:

1. Fill the Host name field with the ftp server name (with or without ftp://)
1. Fill the Port field or leave it empty to use the default value (by default 21)
1. Fill the User field with the ftp account user name
1. Fill the Password with the ftp account user password
1. Fill the Folder path with the relative path on the ftp server
1. Click Save
1. Click the Publish website ribbon button in the Website tab
