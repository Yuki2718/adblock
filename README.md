# adblock

## medium_mode
### ublock-dynamic-rules.txt

A whitelist for medium mode of uBlock Origin, meant for English user. The purpose is to help those non-techie, yet security-conscious, people to use the mode. Payment services and mobile sites are out-of-scope. This is not a list I myself use so won't be updated frequently.

### ublock-dynamic-rules-plus.txt

`* localhost * block`

`file-scheme * 1p-script block`

`file-scheme * inline-script block`

in addition to ublock-dynamic-rules.txt

### ublock-static-rules.txt

WordPress plugins have been security nightmare and are usually implemented in first-party resource that bypasses medium mode. Although it's impossible to block thousands of these plugins without breaking too many sites, blocking those unwanted plugins won't be a bad idea. While popular social and annoyances filters block many of them, they come with tons of unnecessary rules[^1] and also occasionally cause false positive. For these reasons I've settled down to AdGuard Social media filter which is relatively small in size and rarely breaks pages; however, it only blocks minimal set of the plugins. This list includes 1) rules for the plugins not on the Social media filter or other default filter lists, 2) rules almost equivalent to Noscript's Application Boundaries Enforcer, and 3) a regex rule focused only on the latest survey scam campaign.

Exclusion:
rules that caused or can cause false positive
rarely seen plugins such that used by less than 100 sites according to themesinfo.com
CSS-only plugins; those generic rules can have performance impact so I guess blocking CSS-only plugins does not pay enough.

[^1]: Unnecessary network rules if you use medium mode and tons of cosmetic rules; cosmetic rule has no security or privacy value.

### medium-mode-plus-backup.txt

uBlock Origin backup file that incorporates all the above rules on top of default settings + AdGaurd Social meddia filter


## no_gen_cosm
### ublock-cosmetic-rules.txt

`Ignore generic cosmetic filters` is recommended if you want better performance without sacrificing security or privacy. However, you'll notice broken layout of many websites once you enabled this option. This filter adds two semi-generic cosmetic rules to mitigate the layout issue. Those TLD in the list are what I've confirmed the rule is useful on 2+ sites under the domain.
