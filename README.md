# Slight backup android program

[<img src="https://f-droid.org/badge/get-it-on.png"
      alt="Get it on F-Droid"
      height="80">](https://f-droid.org/packages/de.shandschuh.slightbackup/)

Copyright (c) 2011-2013 [Stefan Handschuh](https://github.com/handschuh)

The file "LICENSE" contains the license information for the program.


This small program allows you to backup and restore specific data of your
android device:
 * SMS (only if the standard application is used)
 * Call-logs (no voicemails)
 * Settings (experimental)
 * Bookmarks (only stock browser; no folders are supported)
 * Playlists
 * User dictionaries
 * Contacts (experimental, see below)

The backups are stored unencrypted in an editable location (standard: sdcard).


## Contacts import/ export

The contacts import and export is performed via the android internal vcs
capabilities.

For exporting contacts, Slight backup just tells the underlying android api to
create the vcs text for each contact. Afterwards the individual strings are
getting bundled into a single xml file.

Importing contacts is slightly more complicated. In a first phase, the program
gathers information about the currently available contacts in order to avoid
duplicates. Then the vcs strings of the detected to be non-existent contacts are
put together into one single vcs file which will be sent to the android api for
import.

Since the vcs texts do not contain information about the "starred" property of a
certain contact, this property will *not* be restored during the import.

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/handschuh/Slight-backup.
