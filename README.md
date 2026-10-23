# Core GRC Cookie Consent for Google Tag Manager

A Google Tag Manager tag template that shows your [Core GRC](https://core-grc.com) cookie consent banner and sets Google Consent Mode: default consent before the visitor chooses, then an update with their choice.

Default consent and consent updates come from your website's Google Consent Mode settings in Core GRC, per region. Change them in Core GRC and publish: Tag Manager picks them up automatically.

Setup guide: https://core-grc.com/docs/google-tag-manager

## Quick start

1. In Google Tag Manager, open **Templates → Search Gallery**, find **Core GRC Cookie Consent** and add it to your workspace.
2. Create a tag from it with your **Website ID** and **Site API key**. Both are in Core GRC under **Cookie Consent → Websites → your website → Install Script → Google Tag Manager**.
3. Fire it on **Consent Initialization - All Pages**, and on no other trigger.
4. Publish your container.

## What the tag does

- Sets Google Consent Mode defaults for all seven consent types from your Core GRC settings, per region.
- Until the Core GRC script has saved those settings in the visitor's browser (usually their first page), uses the tag's first-visit baseline: one checkbox per type, preset to everything denied except `security_storage`, all of them yours to change.
- Updates Consent Mode straight away with a returning visitor's saved choice.
- Loads the Core GRC banner, unless the Core GRC script is already in your website code.
- Updates Consent Mode each time the visitor makes or changes a choice.

## Permissions

| Permission | Why |
| --- | --- |
| Accesses consent state | Sets the Consent Mode defaults and updates. |
| Injects scripts | Loads the Core GRC banner from the Core GRC CDN. |
| Reads cookie values (`coregrc_cc` only) | Reads the visitor's saved choice. |
| Reads local storage (`coregrc-gcm-settings` only) | Reads your website's Consent Mode settings, saved by the Core GRC script. No visitor data. |
| Accesses global variables | Shares consent with the Core GRC banner script. |
| Writes to the data layer (`ads_data_redaction`, `url_passthrough`) | Applies those two options when you tick them. |
| Logs to console | Logs in Tag Manager Preview only. |

## Support

Open an issue in this repository, or contact Core GRC support.

## License

Apache 2.0. See [LICENSE](LICENSE).
