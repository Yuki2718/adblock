# adblock

<strong>Personal filters and rules for AdGuard/uBlock Origin</strong>

<strong>Some filters/rules are renamed for better management. If you've subscribed them you'll need to update the URL. Thank you for your understanding.</strong>

I can't guarantee these filers won't cause problems. If you found problems, report it by the same style as official AdGuard or uBlock filters' issue tracker; otherwise reports can be ignored. Anyone who uses any of my filters/codes shall be deemed to have agreed that I have no responsibility or liability for costs, losses, damages, etc. arising from the use of the filters/codes. Unless Subscribe link is provided these filters are assumed to be copied and pasted, or imported, into My filters/rules (uBlock Origin) or User Rules (AdGuard). They are not what I use and shared solely for others' sake, so please don't blame me if I haven't updated for a while.

<details>
<summary><strong>adguard</strong></summary>

<strong>Do NOT check the "Trusted" box if you subscribe these!</strong>
Because not needed. Trusted filters can inject javascript into pages and thus can potentially be risky. Of course I'm not going to do anything nasty with any of my filters, but imagine what if my Github account was hacked. I'd like to encourage a basic security practice.

### AdGuard Social media Plus (social-plus.txt)

[AdGuard Social media filter](https://kb.adguard.com/en/general/adguard-ad-filters#social) tends to rely too much on cosmetic filters IMHO. This filter consists of network filters only and complements Social media filter. Particularly useful on browser extensions and contents blocker, not as much on other AdGuard platforms where it can remove contents specified by cosmetic filters.
- `||connect.facebook.net^*/sdk.js`
- `||platform.twitter.com/widgets.js`
- `||static.evernote.com^$third-party`

are commented out as some people will need them. Those who are sure don't need them can add them to User Rules without the initial `!`.

Exclusion:
- Follow buttons & comment widgets - they can be useful to some people and often Social media filter doesn't block them.

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/social-plus.txt&title=AdGuard%20Social%20media%20Plus">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/social-plus.txt)

### AdGuard Tracking Protection Plus (tracking-plus.txt)

[AdGuard Tracking Protection filter](https://kb.adguard.com/en/general/adguard-ad-filters#privacy) is probably the least false-positive prone anti-tracking list; however, it comes with its own cost of less coverage which this filter aims to complement. Some of bug reports are commented out but you can add them to User Rules without the initial `!`.

Inclusion criteria:
- Didn't and less likely to cause false-positive
- Useful to English user
- Useful to default-deny script settings such as uBlock Origin medium mode

Exclusion:
- Trackers covered by Simplified domain names filter or Firefox tracking protection
- Trackers blocked by uBlock Origin medium mode with /medium_mode/ublock-dynamic-rules.txt minus EasyPrivacy & Peter Lowe

Acknowledgement: some of its rules are taken from [EasyPrivacy](https://easylist.to/) after I confirmed they 1) are actually in use, 2) are not covered by AdGuard Tracking Protection filter, and 3) apparently haven't caused false positives on my regular browsing.

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/tracking-plus.txt&title=AdGuard%20Tracking%20Protection%20Plus">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/tracking-plus.txt)

</details>

<details>
<summary><strong>japanese</strong></summary>

[日本語](/japanese/README-JP.md)

<strong>If you are a non-Japanese seeking for a good Japanese filter, my first recommendation is [AdGuard Japanese filter](https://kb.adguard.com/en/general/adguard-ad-filters#japanese)</strong>. My filters include some aggressive rules not well-tested outside Japanese sites and likely to cause false positive on your local sites. They are made to address a peculiar situation among Japanese ad-block user that many of them unsubscribe default lists and keep only a Japanese filter. If you proceed, you shall be deemed to have read the [Japanese README](/japanese/README-JP.md) which gives more details, because those who need my filters should be able to read it.

### uBlock Japanese filters

The most comprehensive, block-first, and efficient Japanese list for uBlock Origin that removes ads and analytics on desktop, designed for advanced user. Some of its rules are taken from - or rather intentionally made to be identical with - [EasyList, EasyPrivacy,](https://easylist.to/) [AdGuard Base, AdGuard Tracking Protection, ](https://kb.adguard.com/en/general/adguard-ad-filters) [uBlock Built-in lists,](https://github.com/uBlockOrigin/uAssets/) [Peter Lowe's list,](https://pgl.yoyo.org/adservers/) [Fanboy's Enhanced Trackers List, ](https://www.fanboy.co.nz/filters.html) [EasyList China,](http://abpchina.org/forum/forum.php) [RU AdList](https://forums.lanik.us/viewforum.php?f=102) and [280blocker domain list](https://280blocker.net/files/280blocker_domain_ag.txt)sup>1</sup>. This way even if an user added any of those lists (which is uncommon in Japanese adblock user) along with my list, those duplicates will be discarded and can do no harm. This list is also strongly influenced by [Tofu filter](http://tofukko.r.ribbon.to/abp.html) though rules are not directly taken for copy right problems.

1: Only uBlock Built-in and 280blocker domain list are out of CC BY-SA license. I hope and believe rules taken from them are within a range of what filter authors can generally think of.

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt&title=uBlock%20Japanese%20filters">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt)

### uBlock Japanese filters - Paranoid

This can be added to uBlock Japanese filters for enhanced blocking. Use at your own risk. Some rules are taken from or influenced by [EasyPrivacy,](https://easylist.to/) and [Fanboy's Enhanced Trackers List, ](https://www.fanboy.co.nz/filters.html).

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt&title=uBlock%20Japanese%20filters%20-%20Paranoid">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-paranoid.txt)

### uBlock Japanese filters - Social

Removes share buttons mainly on Japanese sites. Some rules are taken from [AdGuard Social media](https://kb.adguard.com/en/general/adguard-ad-filters#social).

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt&title=uBlock%20Japanese%20filters%20-%20Social">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt)

### uBlock Japanese filters - Annoyances

Removes annoyances mainly on Japanese sites. Some rules are taken from or influenced by [AdGuard Annoyances](https://kb.adguard.com/en/general/adguard-ad-filters#annoyances-filter) and [Fanboy Annoyances](https://www.fanboy.co.nz/index.html).

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt&title=uBlock%20Japanese%20filters%20-%20Annoyances">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances.txt)


### blog-parts-adult.txt

See below, this is a variant of blog-parts.txt for adult sites. Included in uBlock Japanese filters - Annoyances

### blog-parts.txt

This removes blog parts and ranking buttons on Japanese websites. Included in uBlock Japanese filters - Annoyances

Exclusion:
- Potentially useful parts or buttons
- Buttons for simple search sites without ranking function
- Buttons on adult sites except for some common ones (see above)

### Sable filters 2 (sable-filters2.txt)

Inspired by [Sable filters](http://meetingwords.com/RK2njtyC7k), this removes cookie consents. Main targets are Japanese sites and other high-traffic sites many Japanese people may visit. False-positive prone rules won't be added. Included in uBlock Japanese filters - Annoyances

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt&title=Sabre%20filters%202">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt)

</details>

<details>
<summary><strong>medium_mode</strong></summary>

All the filters/rules in this category are for uBlock Origin.

### anti-allowlist.txt

This is to counter unnecessary or too generic allowlists which were not addressed or won't be addressed by the maintainer. Only for advanced user as it can cause problems.

### dynamic-rules-mob.txt

See below, it's a mobile version of ublock-dynamic-rules.txt.

### dynamic-rules.txt

Nooplists for medium mode of uBlock Origin dedicated for English user. The objective is to help those non-techie, yet security-conscious, people to use the mode. Payment services and mobile sites are out-of-scope. In addition, following rules are included:

- `* localhost * block`
- `file-scheme * 1p-script block`
- `file-scheme * inline-script block`

Q: Why X is nooped, it's bad!
A: See the purpose, this list is built to make as few breakage as possible for as many English user. This doesn't mean it should be used 'as is' - still each user should train their rules. Even with lax rules medium mode is much better than easy mode in terms of blocking.

### static-rules.txt

WordPress plugins have been security nightmare and are usually implemented in first-party resource that bypasses medium mode. Although it's impossible to block thousands of these plugins without breaking too many sites, blocking those unwanted plugins won't be a bad idea<sup>1</sup>. While popular social and annoyances filters block many of them, they come with tons of unnecessary rules<sup>2</sup> and also occasionally cause false-positive. For these reasons I've settled down to AdGuard Social media filter and uBlock filters - Annoyances which are relatively small in size and rarely break pages; however, they only block minimal set of the plugins. This list includes 1) rules for the plugins not on Social media filter or other default filter lists, 2) rules almost equivalent to Noscript's Application Boundaries Enforcer (thanks to @gwarser), and 3) a regex rule focused only on the latest survey scam campaign.

Exclusion:
- rules that caused or can cause false-positive
- rarely seen plugins such that used by less than 100 sites according to themesinfo.com or plugins used only on specific websites
- CSS-only plugins

1: It doesn't make sense if the site was fully compromised, but is some other cases may protect you from malwarized plugins and some vulnerabilities.

2: Unnecessary network rules if you use medium mode and tons of cosmetic rules; cosmetic rule has no security, privacy, or performance value.
</details>

<details>
<summary><strong>no_gen_cosm</strong></summary>

### Placeholder Hider with no generic hiding (phhider.txt)

`Ignore generic cosmetic filters` is recommended if you want better performance without sacrificing security or privacy. However, you'll notice ugly layout of many websites once you enabled this option<sup>1</sup>. This filter mitigates this on English sites by removing placeholders left as a result of disabling generic cosmetic filters. Useful to those who replaced EasyList with its "without element hiding" version too. The name is inspired by [Placeholder Buster](https://github.com/NanoAdblockerLab/NanoContrib) but the list is independent and can be used together. I also highly recommend you to add AdGuard Base in uBlock Origin's stock lists not only because it includes many specific cosmetic rules but also many potential problems by my rules are already addressed by the list. This would probably be the first public list utilizing [specific generic filter](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax#specific-generic).

Exclusion:
- Small place holder (e.g. *##.ad-space or *##.ad-area hides placeholders on various WordPress sites but won't be added for the reason.)
- Placeholders covered by AdGuard Base

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider.txt&title=Placeholder%20Hider%20with%20no%20generic%20hiding">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider.txt)

1: Another side effect is any filter lists that heavily depend on generic cosmetic filters don't work well. An example of such list is Fanboy Annoyances List.

### Placeholder Hider with no generic hiding for mobile (phhider-mob.txt)

See above, it's a mobile version of phhider-nogen.txt. Rules covered by AdGuard Mobile ads filter won't be added.

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider-mob.txt&title=Placeholder%20Hider%20with%20no%20generic%20hiding%20for%20mobile">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider-mob.txt)

</details>

#### Notable users of my lists

[dbl.oisd.nl | Internet's #1 domain blocklist](https://oisd.nl/)

[spirillen's uBlockOrigin Rules](https://gitlab.com/AnonymousPoster/ublockorigin-rules)
