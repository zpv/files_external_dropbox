# files_external_dropbox
Flysystem based dropbox backend for Nextcloud  
Original patch by [icewind1991](https://github.com/icewind1991/files_external_dropbox)

Fixes missing subdirectory issues.

Requires Nextcloud 12.0 or later

## Steps For Installation:
- Get the code
```bash
git clone
cd files_external_dropbox
composer install
```
- Move this folder ```files_external_dropbox``` to `nextcloud/apps`
- Activate the app from settings page
- Fill up the storage details (See Below _Configuring OAuth2_)
- Fire up the files page to see the ```Dropbox``` mounted as external storage

## Configuring OAuth2
- Connecting Dropbox is a little more work because you have to create a Dropbox app. Log into the [Dropbox Developers](http://www.dropbox.com/developers) page and click Create Your App
- Then choose which folders to share, or to share everything in your Dropbox.
- Name Your App and then click Create App
- Under the section **OAuth2** Redirect URIs add a new URL ```http://path/to/nextcloud/index.php/settings/admin?sectionid=storage``` _(Replace http://path/to/Nextcloud/index.php with you valid Nextcloud installation path)_
- Then Go to Nextcloud```/settings/admin/externalstorages``` and Add a new storage **Dropbox V2** 
- Fill the details Client Id, Client Secrets from you Dropbox App page
- Click Grant Access and then you will be redirected for OAuth login
- After completing the OAuth you will be redirect back to Storage Section and you should see **green** mark along your storage configuration
- That's it

## Dependencies
This app depends on the flysystem adapter for dropbox which can be found here [https://github.com/Hemant-Mann/flysystem-dropbox](https://github.com/Hemant-Mann/flysystem-dropbox)


## Future Work
- Update the Guzzle Dependency to ^6.0