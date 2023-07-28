# Islandora File Transmission Fixity

## Overview

This module allows a user who is uploading a file as a media attachment to enter
that file's sha1 checksum.  The checksum will be tested for validity before the
upload begins, and will be compared to the checksum of the file once uploaded.
A message indicating success or failure will be shown on the screen, and persisted
to the media.

## To use

Two fields will have to be added to each media type for which checksumming is
desired - one for the expected checksum, and one to hold the actual checksum of
the file once received.  The default file fields are `field_expected_checksum` and
`field_actual_checksum`, but these can be changed in configuration at
`/admin/config/islandora_file_fixity/settings`.

Before a file is uploaded the user will have to determine the sha1 of the existing
file.  On a Macbook this means typing `shasum /path/to/file` from as terminal window,
on as Windows machine it's `CertUtil -hashfile <path to file> SHA1`

I recommend the [Read only File Widget](https://www.drupal.org/project/readonly_field_widget)
to display `field_actual-checksum` but its not necessary.

## Credits

This module is extracted from the [Islandora RDM Transmission Fixity module](https://github.com/roblib/islandora_rdm/tree/8.x-1.x/islandora_rdm_file_transmission_fixity) 
so that it can be used as a stand-alone module. Original module created with the support of CANARIE grant funding by the team at Robertson Library, University of PEI.
