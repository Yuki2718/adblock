# adblock

<strong>Personal filters and rules for AdGuard/uBlock Origin</strong>

I can't guarantee these filers won't cause problems. If you found problems such as broken layout, report it by the same style as official uBlock filters' issue tracker; otherwise reports can be ignored. Anyone who uses any of my filters/codes published here shall be deemed to have agreed that I have no responsibility or liability for costs, losses, damages, etc. arising from the use of the filters/codes. Unless Subscribe link is provided these filters are assumed to be copied and pasted into My Filters (uBlock Origin) or User Rules (AdGuard).

<details>
<summary><strong>adguard</strong></summary>

### AdGuard Social media Plus (adguard-social-plus.txt)

[AdGuard Social media filter](https://kb.adguard.com/en/general/adguard-ad-filters#social) tends to rely too much on cosmetic filters IMHO. This filter consists of network filters only and complements Social media filter. Particularly useful on browser extensions and contents blocker, not as much on other AdGuard platforms where it can remove contents specified by cosmetic filters.
- `||connect.facebook.net/en_US/sdk.js`
- `||platform.twitter.com/widgets.js`
- `||static.evernote.com^$third-party`

are commented out as some people will need them. Those who are sure don't need them can add them to User Rules without the initial `!`.

<a href="https://subscribe.adblockplus.org?location=https%3A%2F%2Fraw.githubusercontent.com%2FYuki2718%2Fadblock%2Fmaster%2Fadguard%2Fadguard-social-plus.txt&amp;title=AdGuard%20Social%20media%20Plus">Subscribe</a>

### AdGuard Tracking Protection Plus (adguard-tracking-plus.txt)

[AdGuard Tracking Protection filter](https://kb.adguard.com/en/general/adguard-ad-filters#privacy) is probably the least false-positive prone anti-tracking list; however, it comes with its own cost of less coverage. This filter aims to complement that and was extracted from my mobile filters but not identical. Some of bug reports are commented out but you can add them to User Rules without the initial `!`.

Inclusion criteria:
- Didn't and less likely to cause false-positive
- Useful to English user
- Useful to default-deny script settings such as uBlock Origin medium mode

Exclusion:
- Trackers covered by Simplified domain names filter or Firefox tracking protection
- Trackers blocked by uBlock Origin medium mode with /medium_mode/ublock-dynamic-rules.txt minus EasyPrivacy

<a href="https://subscribe.adblockplus.org?location=https%3A%2F%2Fraw.githubusercontent.com%2FYuki2718%2Fadblock%2Fmaster%2Fadguard%2Fadguard-tracking-plus.txt&amp;title=AdGuard%20Tracking%20Protection%20Plus">Subscribe</a>

</details>

<details>
<summary><strong>japanese</strong></summary>

### blog-parts-adult.txt

Removes ranking buttons on adult sites. See below.

### blog-parts.txt

This removes blog parts and ranking buttons on Japanese websites.

Exclusion:
- Potentially useful parts or buttons
- Buttons for simple search sites without ranking function
- Buttons on adult sites except for some common ones (see above)

### Sable filters 2 (sable-filters2.txt)

Inspired by [Sable filters](http://meetingwords.com/RK2njtyC7k), this removes cookie consents. Main focuses are Japanese sites and other high-traffic sites many Japanese people will visit. False-positive prone rules won't be added (e.g. cookielaw.org, uk-cookie-consent plugin).

<a href="https://subscribe.adblockplus.org?location=https%3A%2F%2Fraw.githubusercontent.com%2FYuki2718%2Fadblock%2Fmaster%2Fjapanese%2Fsabre-filters2.txt&amp;title=Sabre%20filters%202">Subscribe</a>

</details>

<details>
<summary><strong>medium_mode</strong></summary>

### ublock-dynamic-rules.txt

A whitelist for medium mode of uBlock Origin for English user. The purpose is to help those non-techie, yet security-conscious, people to use the mode. Payment services and mobile sites are out-of-scope. In addition, following rules are included:

- `* localhost * block`
- `file-scheme * 1p-script block`
- `file-scheme * inline-script block`

### ublock-static-rules.txt

WordPress plugins have been security nightmare and are usually implemented in first-party resource that bypasses medium mode. Although it's impossible to block thousands of these plugins without breaking too many sites, blocking those unwanted plugins won't be a bad idea. While popular social and annoyances filters block many of them, they come with tons of unnecessary rules<sup>1</sup> and also occasionally cause false-positive. For these reasons I've settled down to AdGuard Social media filter which is relatively small in size and rarely breaks pages; however, it only blocks minimal set of the plugins. This list includes 1) rules for the plugins not on the Social media filter or other default filter lists, 2) rules almost equivalent to Noscript's Application Boundaries Enforcer, and 3) a regex rule focused only on the latest survey scam campaign.

Exclusion:
- rules that caused or can cause false-positive
- rarely seen plugins such that used by less than 100 sites according to themesinfo.com or plugins used only on specific websites
- CSS-only plugins; those generic rules can have performance impact so I guess blocking CSS-only plugins does not pay enough.

Click on the Raw button of the page and copy & paste the code to your uBlock Origin's My filters pane.

[1]: Unnecessary network rules if you use medium mode and tons of cosmetic rules; cosmetic rule has no security, privacy, or performance value.
</details>

<details>
<summary><strong>no_gen_cosm</strong></summary>
  
### Placeholder Hider with no generic hiding (phhider-nogen.txt)

`Ignore generic cosmetic filters` is recommended if you want better performance without sacrificing security or privacy. However, you'll notice ugly layout of many websites once you enabled this option. This filter mitigates this on English sites by removing placeholders left as a result of disabling generic cosmetic filters. Useful to those who replaced EasyList with its "without element hiding" version for even better performance too. The name is inspired by [Placeholder Buster](https://github.com/NanoAdblockerLab/NanoContrib) but the list is independent and can be used together. I also highly recommend you to add AdGuard Base in uBlock Origin default set of filters not only because it includes many specific cosmetic rules but also many potential problems by my rules are already addressed by the list. This would probably be a first public list utilizing [specific generic filter](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax#specific-generic)

Exclusion:
- Small place holder (e.g. *##.ad-space or *##.ad-area hides placeholders on various WordPress sites but won't be added for the reason.)

<a href="https://subscribe.adblockplus.org?location=https%3A%2F%2Fraw.githubusercontent.com%2FYuki2718%2Fadblock%2Fmaster%2Fno_gen_cosm%2Fphhider-nogen.txt&amp;title=Placeholder%20Hider%20with%20no%20generic%20hiding">Subscribe</a>

### Placeholder Hider with no generic hiding for mobile (phhider-nogen-mob.txt)

The mobile version of the above filter. This filter will not get updated often due to maintenance cost. Rules covered by AdGuard Mobile ads filter won't be added.

<a href="https://subscribe.adblockplus.org?location=https%3A%2F%2Fraw.githubusercontent.com%2FYuki2718%2Fadblock%2Fmaster%2Fno_gen_cosm%2Fphhider-nogen-mob.txt&amp;title=Placeholder%20Hider%20with%20no%20generic%20hiding%20for%20mobile">Subscribe</a>

</details>
