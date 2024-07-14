# nextcloud-nginx
NextCloud file sharing with Nginx proxy

P.S:
1. External drives don't work properly with docker containers.
2. SSL certificates can be issued to domain names & public IPs only, not to Reserved/Private IPs.

Commands:
1. To remove missing-index warning, use : docker exec --user www-data \<nextcloud-container-id\> php occ db:add-missing-indices
2. To check trusted domains, use: docker exec --user www-data \<nextcloud-container-id\> php occ config:system:get trusted_domains
3. To add new trusted domain, use: docker exec --user www-data \<nextcloud-container-id\> php occ config:system:set trusted_domains \<index\> --value=\<domain-name\>
4. To remove maintenance window warning, use: docker exec --user www-data \<nextcloud-container-id\> php occ config:system:set maintenance_window_start --type=integer --value=1 (1 AM UTC)
5. To remove memcache warning, use: 
