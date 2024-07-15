# nextcloud-nginx
NextCloud file sharing backed by postgres-db & redis with Nginx proxy

P.S:
1. External drives don't work properly with docker containers.
2. SSL certificates can be issued to domain names & public IPs only, not to Reserved/Private IPs.

Commands:
1. To remove missing-index warning, use : docker exec --user www-data \<nextcloud-container-id\> php occ db:add-missing-indices
2. To check trusted domains, use: docker exec --user www-data \<nextcloud-container-id\> php occ config:system:get trusted_domains
3. To add new trusted domain, use: docker exec --user www-data \<nextcloud-container-id\> php occ config:system:set trusted_domains \<index\> --value=\<domain-name\>
4. To remove maintenance window warning, use: docker exec --user www-data \<nextcloud-container-id\> php occ config:system:set maintenance_window_start --type=integer --value=1 (1 AM UTC)
5. To remove default-phone-region warning, use: docker exec --user www-data \<nextcloud-container-id\> php occ config:system:set default_phone_region --value=IN (INDIA)
6. To remove mail server warning, register for a free account @ https://app.sendgrid.com/ and use it's smtp details under Adminnistration Settings > Basic Settings section in NextCloud

Reference: [NextCloud OCC Commands](https://docs.nextcloud.com/server/13/admin_manual/configuration_server/occ_command.html)
