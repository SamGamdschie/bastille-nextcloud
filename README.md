# bastille-nextcloud
BastilleBSD template for Nextcloud.

## Configuration
The template will mount the following host directories
- /werzel/server_config/nginx read-only
- /werzel/server_config/php read-only
- /werzel/server_config/nextcloud read-only
- /werzel/nextcloud
- /werzel/certificates
The first three directories are used to link specific files to certain config files in jail. Thus configuration can be changed from outside jail.
Additionally, the TLS-certificates are used from /werzel/certificates using /www/certificates inside jail. This allows to use another jail to creat letsenrypt certificates.

Also, the nextcloud data directory should point to /www/nextcloud/data using /werzel/nextcloud/data from host.

In future maybe some default configuration will be made available; currently tr to find out.

## Arguments
This template can receive arguments: `php-version` to specify another version for PHP. `mailip` for the internal mail server (MTA) - jail will use sendmail to forward to mailip.
