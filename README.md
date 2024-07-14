# nextcloud-nginx
NextCloud file sharing with Nginx proxy

P.S:
1. External drives don't work properly with docker containers.
2. SSL certificates can be issued to domain names & public IPs only, not to Reserved/Private IPs.
3. To remove missing-index warning, use : docker exec --user www-data <nextcloud-container-id> php occ db:add-missing-indices
