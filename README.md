[![syntax](https://img.shields.io/badge/syntax-AdGuard-%23c61300.svg)](https://kb.adguard.com/en/general/how-to-create-your-own-ad-filters)
[![syntax](https://img.shields.io/badge/syntax-uBlock%20Origin-%23c61300.svg)](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax)

### Announcement (Nov. 16, 2021) - EOL of a few lists

The following lists will soon become unavailable:
- AdGuard Tracking Protection Plus
- Placeholder Hider with no generic hiding for mobile
- Yuki's uBlock Static Rules
- Yuki's Blog parts filters - Adult

AdGuard Tracking Protection Plus: Since I now have direct write access to AdGuardFilters, there's already not much sense for me to maintain this list.

Placeholder Hider with no generic hiding for mobile: This is probably the least maintained list in this repo, and as I added some specific-generic filters to uBlock filters there's not much value for this list now.

Yuki's uBlock Static Rules: Another less maintained list, now lots of duplicates with other popular lists

Yuki's Blog parts filters - Adult: will be merged to Yuki's Blog parts filters.

I'll wait for a week or so before removal, hoping those who happened to notice this to take an according action beforehand.

# adblock

<strong>Personal filters and rules for AdGuard/uBlock Origin</strong>

I can't guarantee these filers won't cause problems. If you found problems, report it by filling in all the mandatory items in Issue template; otherwise reports can be ignored. Anyone who uses any of my filters/codes shall be deemed to have agreed that I have no responsibility or liability for costs, losses, damages, etc. arising from the use of the filters/codes. Unless Subscribe link is provided these filters are assumed to be copied and pasted, or imported, into My filters/rules (uBlock Origin) or User Rules (AdGuard).

<details>
<summary><strong>adguard</strong></summary>

<strong>Do NOT check the "Trusted" box if you subscribe Social media Plus and/or Tracking Protection Plus!</strong>
Because not needed. Trusted filters can inject javascript into pages and thus can potentially be risky. Of course I'm not going to do anything nasty with any of my filters, but imagine what if my Github account was hacked. I'd like to encourage a basic security practice.

### AdGuard Social media Plus

[AdGuard Social media filter](https://kb.adguard.com/en/general/adguard-ad-filters#social) tends to rely too much on cosmetic filters IMHO. This list consists of network filters only and complements Social media filter.
- `||connect.facebook.net^*/sdk.js`
- `||platform.twitter.com/widgets.js`
- `||static.evernote.com^$third-party`

are commented out as some people will need them. Those who don't need them can add them to User Rules without the initial `!`.

Exclusion:
- Follow buttons & comment widgets - they can be useful to some people and often Social media filter doesn't block them.

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/social-plus.txt&title=AdGuard%20Social%20media%20Plus">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/social-plus.txt)

### AdGuard Tracking Protection Plus

**Update** (2021-03-16): Many things have changed since I published this list. Now I'm a maintainer of the official AdGuard lists so tend to add trackers directly to AdGuard Tracking Protection filter. Therefore, Tracking Protection Plus became more of an experiment field for rules I'm not much sure about false positive. When I published this list, there were many unique entries not found in any other lists, but EasyPrivacy has caught up and to avoid redundancy for those who use all the AdGuard Tracking Protection, EasyPrivacy, and this list I consolidated to EasyPrivacy's writing as far as the likelihood of false positive by doing so is not high. As a result, now this list has many duplicates with EasyPrivacy.

[AdGuard Tracking Protection filter](https://kb.adguard.com/en/general/adguard-ad-filters#privacy) is probably the least false-positive prone anti-tracking list; however, it comes with its own cost of less coverage on average which this filter aims to complement. Some of bug reports are commented out but you can add them to User Rules without the initial `!`. Some rules are taken from [EasyPrivacy](https://easylist.to/) after I confirmed they 1) are actually in use, 2) are not covered by AdGuard Tracking Protection filter, and 3) apparently haven't caused false positives on my regular browsing.

Inclusion criteria:
- Didn't and less likely to cause false-positive
- Useful to English user
- Useful to default-deny script settings such as uBlock Origin medium mode

Exclusion:
- Trackers covered by Simplified domain names filter or Firefox tracking protection
- Trackers blocked by uBlock Origin medium mode with /medium_mode/ublock-dynamic-rules.txt minus EasyPrivacy & Peter Lowe's list

**About CNAME tracker:** 

**Update** (2021-03-16): Many people now know AdGuard published CNAME tracker lists. As I wrote below, one should note even without such lists or CNAME uncloaking EasyPrivacy already blocked at least 70% of CNAME tracker all over the world. From the perspective of a filter author, CNAME tracker is no different from other tracker - we inspect script or request and if it sends unnecessary user data we block it unless doing so causes trouble. In fact, I am the first one opened an issue in the AdGuard's CNAME tracker repository to expand its coverage - some of CNAME tracker I proposed were not blocked not only by AdGuard but also by other services such as NextDNS because the trackers were unknown to them. CNAME uncloaking is done by checking the tracker's canonical name in known tracker database so is helpless against unknown tracker, and there are always such trackers out there.

I really don't understand why it's so special to some people. Apparently they still believe subscribing a dedicated anti CNAME tracker list is mandatory to block them if a DNS-level blocker is not deployed on an other layer. The fact is EasyPrivacy alone, or the combination of AdGuard Tracking Protection and my list, blocks about [70% of CNAME tracker](https://blog.apnic.net/2020/08/04/characterizing-cname-cloaking-based-tracking/) while DEFINITELY many other analytics and trackers have slipped whatever your lists through, as long as you visit many sites. You prefer to double-lock a window and keep the door open? CNAME tracker is NOT at all harder to block and filter authors know much more serious circumvention. Of note, Google provides [Server-side Tagging](https://developers.google.com/tag-manager/serverside) as [announced](https://twitter.com/SimoAhava/status/1222459714614841346?s=20) in early 2020. This utilizes A or AAAA record, which is very well expected at the time of the CNAME fuss<sup>1</sup>. It's weird those who made fuss about CNAME cloaking seem to be silent about this. All these remind me that many people keep NoCoin despite EasyPrivacy + uBlock filters - Resource abuse covers 99% of them, and that others keep Adblock Warning Removal with a completely wrong assumption it has something to do with anti-adblock wall. Don't be fooled by misinformation on the Internet.

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/tracking-plus.txt&title=AdGuard%20Tracking%20Protection%20Plus">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/tracking-plus.txt)

<sub>1: uBlock Origin can now fight against this by [strict3p](https://github.com/gorhill/uBlock/commit/bde3164eb445a4e74acca303ec9fa07f82ba1b1c) option.</sub>

### Anti Anti-adblock Enhancer for AdGuard

<strong>Check Trusted box if you use this list as you trust me! To get the most of the list, you have to turn HTTPS filtering on AND DNS filtering OFF. It's not that I recommend to turn DNS filtering off generally, but that this list requires doing so for full function.</strong>

Enhances anti anti-adblock capability of AdGuard by generic filters. Works on AdGuard for Windows, AdGuard for Android, AdGuard for Mac, and AdGuard Browser Extensions but not for AdGuard for Safari, AdGuard for iOS, and AdGuard Contents Blocker. The list never address individual cases so report blocker detection to AdGuard and not here. This list also mitigates malicious popups often seen on porn sites, pirate sites, and/or short links. Since most of filters are taken from uBlock filters, this list is provided under the same license of GPLv3.

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/anti-antiadb.txt&title=Anti%20Anti-adblock%20Enhancer%20for%20AdGuard">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/anti-antiadb.txt)

</details>

<details>
<summary><strong>japanese</strong></summary>

[日本語](/japanese/README-JP.md)

<strong>If you are a non-native Japanese speaker seeking for a good Japanese list, my first recommendation is [AdGuard Japanese filter](https://kb.adguard.com/en/general/adguard-ad-filters#japanese)</strong>. My lists include some aggressive rules not well-tested outside Japanese sites and likely to cause false positive on your local sites. There are also many duplicate rules of uBlock Origin's default lists. These lists are made to address a peculiar situation among Japanese ad-block user that many of them unsubscribe default lists and keep only a Japanese one. If you proceed, you shall be deemed to have read the [Japanese README](/japanese/README-JP.md) which gives more details, because those who need my lists should be able to read it.

### Yuki's uBlock Japanese filters

The most comprehensive, block-first, and efficient Japanese list **only for uBlock Origin** that removes ads and analytics on PC. Some rules are taken from - or rather intentionally made to be identical with - [EasyList, EasyPrivacy](https://easylist.to/), [AdGuard Base, AdGuard Tracking Protection](https://kb.adguard.com/en/general/adguard-ad-filters), [uBlock Built-in lists](https://github.com/uBlockOrigin/uAssets/), [Peter Lowe's list](https://pgl.yoyo.org/adservers/), [Fanboy's Enhanced Trackers List](https://www.fanboy.co.nz/filters.html), [EasyList China](http://abpchina.org/forum/forum.php), [RU AdList](https://forums.lanik.us/viewforum.php?f=102), [280blocker domain list](https://280blocker.net/download/), and [Brave Unbreak](https://github.com/brave/adblock-lists)<sup>1</sup>. This way even if an user added any of those lists along with my list, those duplicates will be discarded and thus can do no harm. This list is also strongly influenced by [Tofu filter](http://tofukko.r.ribbon.to/abp.html) though rules are not directly taken to avoid copy right infringement.

<sub>1: uBlock Built-in and 280blocker domain list are out of CC BY-SA license. I hope and believe rules taken from them are within a range of what filter authors can generally think of.　Brave Unbreak is under MIT license.</sub>

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt&title=Yuki's%20uBlock%20Japanese%20filters">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt)

## Yuki's uBlock Japanese filters - Mobile

Add this if you use Yuki's uBlock Japanese filters with uBlock Origin on Firefox for Mobile.

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-mob.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Mobile">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-mob.txt)

### Yuki's uBlock Japanese filters - Paranoid

This can be added to Yuki's uBlock Japanese filters for enhanced blocking. Use at your own risk. Some rules are taken from or influenced by [EasyPrivacy](https://easylist.to/), [Fanboy's Enhanced Trackers List](https://www.fanboy.co.nz/filters.html), and gwarser's [Block access to LAN](https://github.com/gwarser/filter-lists/blob/master/lan-block.txt) list.

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-paranoid.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Paranoid">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-paranoid.txt)

### Yuki's uBlock Japanese filters - Social

Removes some social elements such as share buttons mainly on Japanese sites. Some rules are taken from [AdGuard Social media](https://kb.adguard.com/en/general/adguard-ad-filters#social).

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Social">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt)

### Yuki's uBlock Japanese filters - Annoyances

Removes annoyances mainly on Japanese sites. Some rules are taken from or influenced by [AdGuard Annoyances](https://kb.adguard.com/en/general/adguard-ad-filters#annoyances-filter), [Fanboy Annoyances](https://www.fanboy.co.nz/index.html), [uBlock filters – Annoyances](https://github.com/uBlockOrigin/uAssets/blob/master/filters/annoyances.txt), and [Web Annoyances Ultralist](https://github.com/yourduskquibbles/webannoyances).

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Annoyances">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances.txt)

### Yuki's uBlock Japanese filters - Annoyances Plus

Removes annoyances which only some user, not everyone, want to remove mainly on Japanese sites.

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances-plus.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Annoyances%2B">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances-plus.txt)

### Yuki's Cookie Dialogue filters (formerly Sable filters 2)

Inspired by [Sable filters](http://meetingwords.com/RK2njtyC7k), this removes cookie consents. Main targets are Japanese sites and other high-traffic sites many Japanese people may visit. False-positive prone rules won't be added. Included in Yuki's uBlock Japanese filters - Annoyances

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt&title=Sabre%20filters%202">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt)

### Yuki's Blog parts filters

Removes blog parts and ranking buttons on Japanese websites. Included in Yuki's uBlock Japanese filters - Annoyances

Exclusion:
- Potentially useful parts or buttons
- Buttons for simple search sites without ranking function
- Buttons on adult sites except for some common ones (see above)

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts.txt&title=Yuki's%20Blog%20parts%20filters">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts.txt)

### Yuki's Blog parts filters - Adult

This is a variant of Yuki's Blog parts filters for adult sites. Included in Yuki's uBlock Japanese filters - Annoyances

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts-adult.txt&title=Yuki's%20Blog%20parts%20filters%20-%20Adult">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts-adult.txt)

### Yuki's Blogroll filters

Removes blogroll (feed-style mutual links) on Japanese sites. Included in Yuki's uBlock Japanese filters - Annoyances

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blogroll.txt&title=Yuki's%20Blogroll%20filters">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blogroll.txt)

### Yuki's Mobile App filters

Blocks mobile app banners. Included in Yuki's uBlock Japanese filters - Annoyances

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/mob-app.txt&title=Yuki's%20Mobile%20App%20filters">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/mob-app.txt)

### Anti-scam enhancer for 280blocker adblock filter（only for AdGuard for Android and uBlock Origin）

Enhance anti-scam capability of [280blocker adblock filter](https://280blocker.net/download/) by utilizing advanced capability of AdGuard/uBlock Origin.

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/280-patch.txt&title=280blocker%20AdblockPlus%E5%BD%A2%E5%BC%8F%20%E6%82%AA%E8%B3%AA%E3%82%B5%E3%82%A4%E3%83%88%E5%AF%BE%E7%AD%96%E5%BC%B7%E5%8C%96%E3%83%91%E3%83%83%E3%83%81">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/280-patch.txt)

</details>

<details>
<summary><strong>medium_mode</strong></summary>

All the filters/rules in this category are for uBlock Origin. dynamic-rules.txt or dynamic-rules-mob.txt can be imported to My rules whereas anti-allowlist.txt and/or static-rules.txt should be copied and pasted into My filters. You can subscribe the latter two instead by importing their raw text URL into Filter lists, but as they are not frequently updated I don't make them subscription filter.

### Yuki's uBlock Anti-allowlist (anti-allowlist.txt)

This is to counter unnecessary or too generic allowlists which were not addressed or won't be addressed by the maintainer. Only for advanced user as it can cause problems.

[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/medium_mode/anti-allowlist.txt)

### Yuki's uBlock Dynamic Rules (dynamic-rules.txt)

Nooplists for medium mode of uBlock Origin dedicated for English user. The objective is to help those non-techie, yet security-conscious, people to use the mode. Payment services and mobile sites are out-of-scope<sup>1</sup>. In addition, following rules are included (Update: removed `* localhost * block` as it causes trouble on some particular case):

- `file-scheme * 1p-script block`
- `file-scheme * inline-script block`

[View Rules](https://raw.githubusercontent.com/Yuki2718/adblock/master/medium_mode/dynamic-rules.txt)

### Yuki's uBlock Dynamic Rules for mobile (dynamic-rules-mob.txt)

Mobile version of Yuki's uBlock Dynamic Rules

[View Rules](https://raw.githubusercontent.com/Yuki2718/adblock/master/medium_mode/dynamic-rules-mob.txt)

Q: Why X is nooped, it's bad!

A: See the purpose, this list is built to make as few breakage as possible for as many English user. This doesn't mean it should be used 'as is' - still each user should train their rules (obviously you have to add many rules if you browse non-English sites). Even with lax rules medium mode is much better than easy mode in terms of blocking.

<sub>1: I live in Japan and don't have full access to US, UK, etc. payment/shopping/banking services. Until you get accustomed to medium mode, it may be advisable to turn medium mode off on such sites. They anyway know much about you.</sub>

### Yuki's uBlock Static Rules (static-rules.txt)

WordPress plugins have been security nightmare and are usually implemented in first-party resource that bypasses medium mode. Although it's impossible to block thousands of these plugins without breaking too many sites, blocking those unwanted plugins won't be a bad idea<sup>2</sup>. While popular social and annoyances filters block many of them, they come with tons of unnecessary rules<sup>3</sup> and also occasionally cause false-positive. For these reasons I've settled down to AdGuard Social media filter and uBlock filters - Annoyances which are relatively small in size and rarely break pages; however, they only block minimal set of the plugins. This list includes 1) rules for the plugins not on Social media filter or other default filter lists, 2) rules almost equivalent to Noscript's Application Boundaries Enforcer (thanks to @gwarser), and 3) a regex rule focused only on the latest survey scam campaign. Want more protection? Assuming you've already using medium mode, you know default-deny approach well. @jawz101 provides a good [wordpress plugins whitelist](https://raw.githubusercontent.com/jawz101/ublockOrigin_wordpressWhitelist/master/my-ublock-static-filters_wordpressWhitelist.txt) which should be used with an entire block rule for the plugin directory.

Exclusion:
- Rules that caused or can cause false-positive
- Rarely seen plugins such that used by less than 100 sites according to themesinfo.com or plugins used only on specific websites
- CSS-only plugins

[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/medium_mode/static-rules.txt)

<sub>2: It doesn't make sense if the site was fully compromised, but in some other cases may protect you from malwarized plugins and some vulnerabilities.</sub>

<sub>3: Unnecessary network rules if you use medium mode and tons of cosmetic rules; cosmetic rule has no security, privacy, or performance value.</sub>
</details>

<details>
<summary><strong>no_gen_cosm</strong></summary>

### Placeholder Hider with no generic hiding (phhider.txt)

`Ignore generic cosmetic filters` is recommended if you want better performance, less false positive, and less chance to encounter anti-adblock without sacrificing security or privacy. However, you'll notice ugly layout of many websites once you enabled this option<sup>1</sup>. This filter mitigates this on English sites by removing placeholders left as a result of disabling generic cosmetic filters. Useful to those who replaced EasyList with its "without element hiding" version too. I also highly recommend you to add AdGuard Base in uBlock Origin's stock lists not only because it includes many specific cosmetic rules but also many potential problems by my rules are already addressed in the list. This would probably be the first public list utilizing [specific generic filter](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax#specific-generic).

Exclusion:
- Small place holder (e.g. *##.ad-space or *##.ad-area hides placeholders on various WordPress sites but won't be added for the reason.)
- Placeholders covered by AdGuard Base

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider.txt&title=Placeholder%20Hider%20with%20no%20generic%20hiding">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider.txt)

<sub>1: Another side effect is any filter lists that heavily depend on generic cosmetic filters don't work well. An example of such lists is Fanboy Annoyances List.</sub>

### Placeholder Hider with no generic hiding for mobile (phhider-mob.txt)

See above, it's a mobile version of phhider-nogen.txt. Rules covered by AdGuard Mobile ads filter won't be added.

Update: Since generic cosmetic filtering is disabled by default on mobile, some specific-generic filters were added to uBlock filters so the value of this list dropped (I already removed entries no more needed - actually I'm the one who proposed and added the filters to uBlock filters). I may stop providing this list in future once I find time to move them to uBlock filters with further check.

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider-mob.txt&title=Placeholder%20Hider%20with%20no%20generic%20hiding%20for%20mobile">Subscribe</a>
[View List](https://raw.githubusercontent.com/Yuki2718/adblock/master/no_gen_cosm/phhider-mob.txt)

</details>

#### Notable users of my lists

[dbl.oisd.nl | Internet's #1 domain blocklist](https://oisd.nl/)

[spirillen's uBlockOrigin Rules](https://gitlab.com/AnonymousPoster/ublockorigin-rules)

#### Acknowledgements

I use [PyFunceble](https://github.com/funilrys/PyFunceble) to screen potential dead domains. I thank all ad- and contents-blocking community members who helped me to learn right filter writing.