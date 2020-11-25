# Anti-tracking, anti-phishing best practices and recommended software

> ## Disclaimer
> People have different views on the risks and consequences of [surveillance capitalism](https://en.wikipedia.org/wiki/Surveillance_capitalism), tracking, or breach of privacy.
> The purpose of these recommendations is to help the awareness of general web users to circumvent blanket tracking and related activities run by tech giants. Or at least to decrease or break up the operational area of these activities both to protect individual rights and to depreciate acquired aggregated information. If you are a high profile, high risk target, probably these pieces of advices are not new.
> While general tracking or even targeted advertising have their fair and respectable use cases and all market players have their right to operate within the law, the current state of surveillance capitalism is considered harmful for both the individual and society on the long term.
> Based on your class, skills and perception of risk you might find some of these tips controversial, even paranoid or just requiring too much commitment for diminishing return to fully enforce them. Apply them at your own judgement.
> It is my personal list of evaluated techniques. It is inherently incomplete and scientifically unproved.

## For all platforms:

- **Use [Firefox](https://www.mozilla.org/en-US/firefox/browsers/)**; [privacy](https://www.mozilla.org/en-US/firefox/privacy/) is part of their mission and their browser has lots of customizable privacy settings. Recommended on both desktop and [mobile](https://www.mozilla.org/en-US/firefox/mobile/).

  - Enable `do-not-track`, `https-only` settings.
  - Enable blocking `3rd party cookies`, `fingerprinting`, `cryptominers`.
  - Enable auto-update of browser and addons
  - **Use containers** (available on desktop only)! They separate your web activities and tracks of social media, email, news, banking, etc, like they'd be done in separate browsers. Also you can, for example, access a service with multiple identities at the same time without the need to switch between them if you keep them in their respective containers. While you can manually assign sites to containers, the following addons provide _automatic_ separation for popular sites: [Facebook](https://addons.mozilla.org/en-US/firefox/addon/facebook-container/), [Google & Youtube](https://addons.mozilla.org/en-US/firefox/addon/google-contain-integrations/), [Twitter](https://addons.mozilla.org/en-US/firefox/addon/twitter-container/). When installed, these tech companies can no longer track your browsing activities outside their sites.

- Do not use Chrome. Since the [operation of adblockers has been restricted recently in Google Chrome](https://www.ghacks.net/2019/10/12/the-end-of-ublock-origin-for-google-chrome/), it is no longer a recommended browser. As Google is a main beneficiary of tracking and targeted advertising, they seem no longer interested in developing open, privacy-aware software. Modern browsers have almost identical features in terms of web standards and capabilities (trust me, I'm a web dev), so use Chrome only if Firefox is not adequate for some reason.

- You may use [Brave](https://brave.com/), which advertises itself as a privacy-aware, fast, adblocker-included browser. But, recently they got caught [manipulating affiliate links without user consent](https://davidgerard.co.uk/blockchain/2020/06/06/the-brave-web-browser-is-hijacking-links-and-inserting-affiliate-codes/), which is a major loss of trust.

- **Use a password manager**

    - [Bitwarden](https://bitwarden.com/) is highly recommended. Open-source, audited, available on _all_ platforms, can also store any custom fields besides website credentials
    - [Lockwise](https://www.mozilla.org/en-US/firefox/lockwise/) (Firefox's own password manager)
    - [1password](https://1password.com/)
    - You only need to remember a single complex master password to use it. Then you have all your other passwords and keys get auto-generated and synced across all your devices. Your stuff is stored in the _Vault_ that is stored encrypted in your computed and/or in the cloud.
    - Password managers auto-fill your passwords on websites (or even in mobile apps). Besides being convenient, this is a great counter-measure to [phishing](https://en.wikipedia.org/wiki/Phishing). You might get tricked to enter your credentials on a fake website, but a password manager can never be made to do that.
    - Cloud-based storage and sync is OK. Your sensitive data is encrypted all the way and even the service provider cannot recover your data without the master password. The master password is not stored in your vault, nor in the cloud. If you forget or lose your master password, you can no longer access your online vault!
    - _Advanced:_ if you are super-sensitive, you can even [host your Bitwarden vault on your own server](https://bitwarden.com/open-source/).

- Use unique, long, complex passwords everywhere. By using a password manager it's as difficult as using simple lame insecure ones, so why not?

- Enable [Two-factor Authentication (2FA)](https://en.wikipedia.org/wiki/Multi-factor_authentication) for all services that support it. It adds an extra security measure beside your existing password (the 1st factor) to your login. There are several 2nd factor solutions (one-time code, time-based code), all providing an independent secret code not derived from other factors. Install an auth app ([Bitwarden Premium](https://bitwarden.com/pricing/), [Google Authenticator](https://support.google.com/accounts/answer/1066447), [Authy](https://authy.com/)) to your phone and computer if applicable.

  1. do NOT user text/sms tokens as 2FA if you can avoid it. It's not secure in transfer and can be hijacked via [social-engineering](https://en.wikipedia.org/wiki/Social_engineering_(security)). Some ancient banks/providers still force its use with no other option. Hopefully soon it'll be a thing of the past.
  1. Authenticator apps or mobile OS notifications ([google prompt](https://support.google.com/accounts/answer/7026266)) are secure, they cannot be spoofed or hijacked.
  1. _Advanced:_ hardware keys provide best security with convenience for a premium price, like [Yubico](https://www.yubico.com/)
  1. In case you lose your phone and cannot do 2FA

     - you need to have your backup codes saved to a secure location
     - or set up your 2FA on multiple devices simultaneously
     - or store your 2FA secrets in your password manager (available in Bitwarden paid plan)

- Use an adblocker as an browser addon, like [ublock-origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) (can be installed on mobile Firefox, too).
Don't just search "adblock" and install random hits; there may be malicious addons behind the term. If unsure, just install from the link [for Firefox](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) or [for Chrome](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm).
Defaults settings are great, but it's recommended to enable your country/language's filter list and some social filter lists. Enable filter list auto-update if available.

- Use custom dns server in your internet connection settings

  - _Advanced:_ Put `1.1.1.1`, `9.9.9.9` IP addresses instead of the ones supplied by your internet service provider (ISP). Your ISP might track your site usage based on your dns queries. Often their servers are slower or unavailable, while [Cloudflare](https://1.1.1.1/), for example, has very fast, low latency availability and they pledge to respect your privacy.
  - That said, be aware that your ISP can still watch your dns traffic, e.g. tracking which sites you visit (but not their content). To prevent this, you need secure dns service ([DoH](https://en.wikipedia.org/wiki/DNS_over_HTTPS) or [DoT](https://en.wikipedia.org/wiki/DNS_over_TLS)) supported by your browser or network.
  - _More advanced:_ install [Pi.hole](https://pi-hole.net/) on your local network, a network-wide adblocker. Can be set up as an [encrypted dns provider](https://docs.pi-hole.net/guides/dns-over-https/).

- Look for alternatives to tech giants' popular services. It diversifies your data patterns and you support alternative/open service providers.

  - ~~Google Maps~~ &rarr; [Openstreetmap](https://www.openstreetmap.org/) (I particularly like [this one for touring/cycling](https://en.mapy.cz/turisticka?l=0)) for the browser, [OSMand](https://osmand.net/) for mobile.
  - ~~Google Search~~ &rarr; [Startpage](https://www.startpage.com), [Duckduckgo](https://duckduckgo.com/)
  - ~~Zoom~~, ~~Facetime~~, ~~Facebook Video~~ &rarr; [Jitsi](https://jitsi.org/) is a free, open-source, feature-rich, end-to-end encrypted, all-platform alternative to all the hyped video-conferencing software.

- Social media
  - Do not disclose your phone number. It may be asked for 2FA, which should be rejected if alternatives are available. If you must make a phone number public, use an alternative one and keep your real one used for 2FA or account recovery private.
  - Do not install all-purpose social media apps on your mobile. It is a major distraction, battery-killer and voluntary privacy surrender (see below). If you insist on keeping social media messaging, consider installing [Messenger Lite](https://play.google.com/store/apps/details?id=com.facebook.mlite) instead of Facebook app. Though it's not [end-to-end encrypted](https://en.wikipedia.org/wiki/End-to-end_encryption).
  - They can track your other browser activities even if you logged out of them and closed their window. That's because their website components (`Like` buttons, Share options) are often included on lots of other websites and by visiting them you download these components with your social media credentials and cookies. To prevent this, you need to log out of social site and clear all cookies associated with them, which is pretty tedious, or you can install the Firefox containers mentioned above to restrict their operations without hassle.
  - Use a messaging app that supports [end-to-end encryption](https://en.wikipedia.org/wiki/End-to-end_encryption), like Whatsapp, [Signal](https://signal.org/), iMessage.

## Specific to mobile

- Switch off wifi/mobile network when not needed. Apps tend to constantly post tracking information to providers and software vendors on active connections even when not actively used. By switching off your unused connections you limit the window of surveillance, usage pattern data, location data, etc.

- Use services/features in mobile web browser rather than mobile app. Apps have more access rights to your personal data, while the browser is [sandboxed](https://en.wikipedia.org/wiki/Sandbox_(computer_security)), has limited access. Also, ad blocking normally works only in the browser, not in apps, unless you use pi.hole or some network-wide blocking mechanism. For instance, Facebook app has access to all your contacts if installed on your phone and cross-reference them with other users' data to target you, while the Facebook website does not.

- Install [Firefox Mobile](https://www.mozilla.org/en-US/firefox/mobile/) with ublock-origin addon instead of factory browser.
