# Nextcloud section

In this folder, is example how to build full dependencies nextcloud docker image.

- Dockerfile
- supervisord.conf

## 	Dockerfile

The Dockerfile uses the offical ```nextcloud:apache``` image as base image and adds dependencies for all optional packages suggested by nextcloud that may be needed for some features.

| Add Dependencies        | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| Cron                    | uses supervisor to run the cron job inside the container (so no extra container is needed). This image runs `supervisord` to start nextcloud and cron as two seperate processes inside the container. Using the cron feature is the preferred method for executing regular tasks. |
| PHP Module imap         | adds dependencies required to authenticate users via imap    |
| PHP Module smbclient    | adds dependencies required to use smb shares for External storage support |
| LibreOffice             | The Dockerfile does not install the LibreOffice package (line is commented), because it would increase the generated Image size by approximately 500 MB. In order to install it, simply uncomment the appropriate line in the Dockerfile. |
| Ffmpeg                  | Support previews.Per default, only previews for BMP, GIF, JPEG, MarkDown, MP3, PNG, TXT, and XBitmap Files are generated. The configuration of the preview generation can be done in config.php, as explained in the [Administration Manual](https://docs.nextcloud.com/server/12/admin_manual/configuration_server/config_sample_php_parameters.html#previews) |
| imagemagick SVG support | SVG support                                                  |
| p7zip and p7zip-full    | Support the [Nextcloud Extract](https://github.com/PaulLereverend/NextcloudExtract) app.(Bring extraction to your nextcloud web interface) |
| PHP Module rar          | Support the [Nextcloud Extract](https://github.com/PaulLereverend/NextcloudExtract) app.(Bring extraction to your nextcloud web interface) |
| PHP Module bz2          | Bz2 support                                                  |
| PHP Module gmp          | gmp support                                                  |

