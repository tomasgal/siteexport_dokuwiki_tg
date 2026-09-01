# SiteExport compatibility fork for DokuWiki Greebo

This repository is a compatibility fork of the DokuWiki **SiteExport** plugin by i-net software.

## Baseline

- Upstream: https://github.com/i-net-software/dokuwiki-plugin-siteexport
- Upstream tag: `2019-02-11`
- Upstream commit: `273152e01ed04ac93bce9b977005798185f42547`
- Tested DokuWiki: **2018-04-22b Greebo**
- Tested PHP: **5.6.40**

The purpose of this fork is to preserve a working SiteExport version for this legacy DokuWiki/PHP stack.

## Local compatibility fixes

Two source files differ from the upstream `2019-02-11` release:

1. `syntax/toc.php`
   - prevents an already resolved TOC page ID from being resolved a second time;
   - fixes cases where an already resolved root-page ID such as `docs` would otherwise become the invalid `docs:docs`.

2. `action/ajax.php`
   - fixes internal link rewriting for flat static exports with DokuWiki `userewrite=2`;
   - namespace-qualified links such as `docs/page` are rewritten to the actually exported flat file `page.html`.

The modified source locations contain explicit comments marking the changes and their date.

## License

This fork remains licensed under the **GNU General Public License version 2**, as the upstream project. Original copyright and license notices are retained.

## Original upstream README

The original documentation is available in the upstream repository and in the `2019-02-11` release history linked above.
