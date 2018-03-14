---
title: Home
---

# Download
Download for Chrome: [Chrome Webstore](https://chrome.google.com/webstore/detail/nzbdonkey/edkhpdceeinkcacjdgebjehipmnbomce)

Download for Firefox: [Firefox Add-on](https://addons.mozilla.org/de/firefox/addon/nzbdonkey/)

# Description
Add-on to automatically download NZB files or send them to NZBGet, SABnzbd or Synology DownloadStation.

Right click on a NZBlnk link and choose "Get NZB file". If no NZBlnk link is provided, select title, header and password, then right click on the selected text and choose "Get NZB file".
By default the extension is also configured to catch left clicks on a NZBlnk link and process them. This can be deactivated in the general settings.

Set the corresponding settings in the settings page in order to send the NZB file directly to NZBGet, SABnzbd or Synology DownloadStation.
The setting options are mostly self explanatory.

Currently in beta testing.
A more detailed description will be added soon.

# Change log
### v0.4.0
* New feature: nzb files can now be checked for completeness. The feature is activated by default but can be deactivated in the general settings. Also the threshold value for missing files and segments can be changed.
  
  **NOTE:** the check for completeness is very basic and limited because it depends mostly on the information provided in the file's subject set by the program used to upload the files to the usenet. Unfortunately there is no official standard for the file's subject for multiple file uploads.
* New feature: a desktop notification will now show up if the script has started to search for the nzb file. Informative notifications (e.g. upon start of the script) will have the standard blue icon. Success notification will have green icon and error notification a red icon for better differentiation.
* Bug fix: context menu will now only show one menu entry if selected text contains a link.
* Bug fix: Errors will now be catched and a error notification will be shown if download of the nzb files to the download folder fails. Also fixed "invalid filename" error if title does contain a zero width space.
* Other: the script will now fall back to storage.local if storage.sync is not available/activated (might help to geth the script running on some officially unsupported browsers).
* Other: some cleanup of the code. Moved repeated code into own functions.

### v0.3.1
* Bug fix for: "nzb.password.match is undefined" bug in processNZBfile routine.

### v0.3.0
* Options page: added a test button on the NZBGet, SABnzbd and Synology DownloadStation settings to test the connection with the server.
* Options page: changed all alerts to modal pop-ups.
* Background Script: Almost a complete rewrite of the background script using promises as far as possible and chaining them together:
  * The stored settings are now only loaded if the script is executed.
  * If an error occurred, in almost all cases a desktop notification will show up presenting the error message.
  * Now all nzb files found will be downloaded and the first valid nzb file will be saved or pushed to the download program.
* Additional minor bug fixes

### v0.2.1
* Bug fix for: Failed to execute 'btoa' on 'Window': The string to be encoded contains characters outside of the Latin1 range.

### v0.2.0
* Added support for Synology DownloadStation.
* Updated Settings Page to show only the relevant tab according to the chosen action for the NZB file.
* Renamed "Search Engines" tab to "Advanced" and added a warning alert.
* Added an option to deactivate success notifications
* Switched all search and download URLs to https where possible. Stored Search Engines settings will be overwritten upon update.
* Changed default for "Catch left mouse clicks on NZBlnk links" to true
* NZB file are now downloaded and pushed to the download programs instead of only pushing the download URL
* Meta data for title, category and password is added to the NZB file before saving it or pushing it to the download programs
* Added an option to reset the settings to the default settings
* Added an option to push the NZB file to SABnzbd as paused
* Changed communication with NZBGet from XML-RPC to JSON-RPC for better handling
* Small improvements to the selection analyzing routine

### v0.1.5
* Bug fix: wrongly named settings variable for category

### v0.1.4
* Quick bug fix of an error introduced with v0.1.3

### v0.1.3
* had to rename a variable to prevent Mozilla reviewers from kicking the add-on out of the store

### v0.1.2
* Settings page redesigned
* NZBGet: password is now passed as a parameter and not as part of the NZB filename
* Bug fix: improved the capturing of left mouse clicks on NZBlnk links