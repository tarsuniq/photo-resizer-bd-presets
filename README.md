# Photo & Signature Resizer BD: presets

The upload rules used by the Photo & Signature Resizer BD Android app. The app fetches
[`presets.json`](presets.json) on launch, so changes here reach users without an app update.

## Making a change

1. Edit `presets.json` (the pencil icon on GitHub works).
2. **Set `updated` to today's date** (`yyyy-mm-dd`). Apps only take a file newer than the one they have.
3. Commit. Apps pick it up on their next launch (GitHub may cache the file for up to 5 minutes).

A file the app can't read is ignored: a wrong `schema`, broken JSON, a missing field or an older `updated`
date leaves users on their last good copy. Still, check the JSON is valid before committing.

## Fields

| Field | |
|---|---|
| `id` | Unique and stable. |
| `rank` | Order on the home screen, lowest first. Change this to reorder. |
| `category` | `jobs`, `admission`, `passport`, `nid`, `visa` or `other`. |
| `name`, `nameBn`, `note`, `noteBn` | Shown to users. Bangla falls back to English when empty. |
| `source`, `verifiedOn` | The official page the rule was read from, and when. Shown to users. |
| `photo`, `signature` | Optional. `width`, `height`, `maxKB`, optional `minKB` and `colourRequired`. Omit both for an information-only entry, which then needs a `note`. |

Only add rules read from the portal's own validator or official instructions.
