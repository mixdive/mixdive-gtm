# Mixdive Google Tag Manager template

The [Mixdive](https://mixdive.com) tag for Google Tag Manager web containers.
Add it from the **Community Template Gallery** (search "Mixdive"), fill in your
server URL and API key, and your site sends visitors, sessions, page views and
your own events to your self-hosted Mixdive server.

Documentation: **https://docs.mixdive.com/integrations/google-tag-manager/**

## What it does

One tag type with four actions:

| Action | Trigger | Fields |
|---|---|---|
| **Initialize Mixdive** | Initialization – All Pages | Server URL, API key, automatic page views (on), app version, console logging |
| **Track event** | your dataLayer triggers | Event name (usually `{{Event}}`), user id, properties table, count / sum / duration, occurrence id |
| **Identify user** | login / sign-up triggers | User id, name, email |
| **Page view** | History Change | Path, only for containers that turn automatic page views off |

Template code cannot make HTTP requests, so the tag loads the Mixdive browser
SDK ([`@mixdive/browser`](https://www.npmjs.com/package/@mixdive/browser),
pinned to one version per template version) from the npm CDN mirror and hands
every action to it through the SDK's call queue. Data goes only to **your**
Mixdive server; the SDK never sends the visitor's IP, full URLs or query
strings, and stays silent in automated browsers.

## Install without the gallery

Templates → **Tag Templates** → **New** → ⋮ → **Import** → choose
`template.tpl` from this repository. The tag then appears under Custom in the
tag picker.

## Development

Edit the template in a GTM container's Template Editor (it validates the
sandboxed code, runs the `___TESTS___` scenarios and manages permissions),
export it, and replace `template.tpl`. To publish a version to the gallery,
commit, then add the commit's SHA to `metadata.yaml`, newest first, and
commit again.

## License

Apache-2.0.
