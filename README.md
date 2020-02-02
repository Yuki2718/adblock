# adblock

## /medium_mode/ublock-dynamic-rules.txt

A whitelist for medium mode of uBlock Origin, meant for English user. The purpose is to help those non-techie, yet security-conscious, people to use the mode. Payment services and mobile sites are out-of-scope. This is not a list I myself use so won't be updated frequently.

## /medium_mode/ublock-static-rules-plus.txt

`* localhost * block`
`file-scheme * 1p-script block`
`file-scheme * inline-script block`
in addition to ublock-dynamic-rules.txt

## /medium_mode/ublock-static-rules.txt

WordPress plugins have been security nightmare and are usually implemented in first-party resource that bypasses medium mode. Although it's impossible to block thousands of these plugins without breaking too many sites, blocking those unwanted plugins won't be a bad idea. While popular social and annoyances filters block many of them, they come with tons of unnecessary rules[^1] and also occasionally cause false positive. For these reasons I've settled down to AdGuard Social media filter which is relatively small in size and rarely breaks pages; however, it only blocks minimal set of the plugins. This list includes rules for the plugins not on the Social media filter and another set of rules almost equivalent to Noscript's Application Boundaries Enforcer.

## /medium_mode/medium-mode-plus-backup.txt

uBlock Origin backup file that incorporates all the above rules on top of default settings + AdGaurd Social meddia filter


[^1]: Unnecessary network rules if you use medium mode and tons of cosmetic rules; cosmetic rule have no security or privacy value.