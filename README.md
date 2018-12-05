# Lighthouse Platform Packs

[Lighthouse](https://github.com/GoogleChrome/lighthouse) is an open-source tool that provides developers with guidance to improve their site. It does this by auditing for performance, accessibility and other best practices.

Many developers today use different technologies (backend/CMS/JavaScript frameworks) to build their web pages. Instead of only surfacing general recommendations, what if Lighthouse could also provide more relevant and actionable advice depending on the tools used?

You can see a prototype of this feature with [Lighthouse Viewer](https://houssein.me/lighthouse/viewer-wordpress/?gist=9efc3fc22dc500620c884db995e3fb6c).

## Contributing

This is still under early development, but we would like to hear any suggestions from community members in the meantime. [WordPress](https://wordpress.com/) is the first ecosystem we would like to include before rolling this out for other platforms. 

* If you're an active member of the WordPress community, feel free to leave PRs and suggestions for different audit messages in [`wordpress/audits.json`](./wordpress/audits.json).
  * For each audit, the `secondaryDescription` attribute can be used to include (or modify) the WordPress specific messages.
* If you have any ideas or suggestions on the design in the prototype, please open an issue!

Before contributing in any way, make sure to also read [CONTRIBUTING.md](./CONTRIBUTING.md).

## Testing changes locally

If you would like to test your changes with Lighthouse Viewer using this prototype, you can do the following:

* In Lighthouse, create a branch off of the [one](https://github.com/housseindjirdeh/lighthouse/tree/wp-advice-pack) used to set up this rough prototype.
* For any audit that you would like to update, open its respective file (the file name always matches the audit `id`)
* Add a [`secondaryDescription`](https://github.com/housseindjirdeh/lighthouse/blob/wp-advice-pack/lighthouse-core/audits/byte-efficiency/offscreen-images.js#L52) to the `meta` static method
* Run `yarn update:sample-json` to update the i18n strings
* Build and run [Lighthouse CLI](https://github.com/GoogleChrome/lighthouse#run) to view the report