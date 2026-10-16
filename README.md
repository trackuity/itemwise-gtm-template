# Itemwise Tag for Google Tag Manager

A Google Tag Manager tag template that loads the [Itemwise](https://www.itemwise.com) tag on your website, respecting your visitors' cookie choices.

## How it works

The template checks Google Consent Mode for `ad_storage` (consent for advertising cookies):

- **Granted**: the Itemwise tag loads right away.
- **Not granted yet**: nothing is loaded or sent. The template waits, and if the visitor accepts later on the same page, the Itemwise tag loads at that moment. It loads at most once per page.

Your cookie banner must set the Google Consent Mode default (`ad_storage` denied) before Google Tag Manager tags run. Google Tag Manager treats a consent type without any state as granted, so without that default the Itemwise tag would load before the visitor has chosen.

## Installation

1. Add the **Itemwise Tag** template to your container from the Community Template Gallery.
2. Create a tag of type **Itemwise Tag** and enter the **Itemwise key** you received from Itemwise.
3. Trigger: **All Pages**. Tag firing options: **Once per page**. Consent Settings: **No additional consent required** (the template waits for consent itself).
4. Test in Preview: before a cookie choice and after rejecting, nothing is requested from `the.itemwi.se`; after accepting, `https://the.itemwi.se/snippet.js` loads.
5. Publish the container.

## Permissions

- **Injects scripts**: `https://the.itemwi.se/snippet.js` only.
- **Reads consent state**: `ad_storage`.
- **Accesses global variables**: `TrackuityObject`, `tty`, `tty.q` and `tty.l`, the queue the Itemwise tag reads its settings from.

## Support

Questions or problems: contact your Itemwise contact person, or open an issue in this repository.
