Automated-Transmit-Uploader
===========================
AppleScript script useful to easily upload files (one or more at the same time) from to a remote server using [Transmit](http://panic.com/transmit/).

## Idea
The idea is based on this http://www.macdrifter.com/2011/09/upload-file-selection-via-transmit.html article.

## Scripts
Automated Transmit Uploader is divided into two scripts. One (`One Click Transmit Uploader`) to be used as a standalone application, the other (`add - Transmit Uploader`) as a folder action.

## Configuration
Both scripts must be configured. The variables to be configured are pretty self explanatory:

    set pathRemote to "/var/www/vhosts/com.example/uploads/"
    set urlBasePath to "http://www.example.com/uploads/"
    set favoriteTransmitConnection to "My Favorite Upload Server"
    set notificationEnabled to true
    set logEnabled to true
    set appName to "One Click Transmit Uploader"

- pathRemote is the upload path on the remote server. Must end with a slash
- urlBasePath is the first part of the url pointing to the location of the uploaded files. Must end with a slash
- favoriteTransmitConnection is the name of the connection added to Transmit. It must be in the *Favorites* group!
- notificationEnabled can be *true* or *false*. Set it true only if you have OS X 10.8 and [terminal-notifier](http://github.com/alloy/terminal-notifier) installed
- logEnabled can be *true* or *false*. If set to *true* writes a log file in your *Documents* directory
- appName is a string that identifies your upload connection. It will be used also to identify the log filename.

## Installation
If you have OS X 10.8 I recommend to install [terminal-notifier](http://github.com/alloy/terminal-notifier).

To install `One Click Transmit Uploader` open the script with *AppleScript Editor* and export it as an application using *Export* from the *File* menu (give the application a name recalling the server you are using). Once you have the application exported, move it to a place you prefer and drag it to the dock. At this point choose a file from the *Finder* and click on the application available in the dock. Once the upload is completed you will have the url pointing to the upload in the clipboard.

To install `add - Transmit Uploader` open the script with *AppleScript Editor* and export it as an **Only Executable** Script using *Export* from the *File* menu (give the script a name recalling the server you are using). Once you have the script exported, move it to the `~/Library/Scripts/Folder Action Scripts/` directory. Choose the directory to be used as the "upload dropbox", Ctrl+click on it and choose *Enable Folder Actions*. You should be able to see your script. If you drag a file in the "upload dropbox" directory you should be able to find in the clipboard the url pointing to the uploaded file.

## Notes
- If you need to upload to more servers, you must configure end export both scripts for all the servers.
- To open the `~/Library/Scripts/Folder Action Scripts/` directory, open a *Finder* window, press Command+Shift+G (or *Go to Folder* from the *Go* menu) and open `~/Library/`. The `Scripts/Folder Action Scripts/` directories, if not available, should be created.
- Sometimes an error is generated using `One Click Transmit Uploader` with files located on the desktop 
