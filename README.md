# cyberine-suite-data

Public data read by every CYBERINE suite app. Nothing here is personal: the files are the same for every user, and the apps send nothing when they fetch them.

## suite_catalog.json

The list of apps in the suite, shown on each app's CYBERINE Apps Toolkit page.

| Field | Meaning |
|---|---|
| `version` | Format version. The apps read version 2. |
| `suite_name` | The suite's name. The apps no longer display it; the page is titled CYBERINE Apps Toolkit in each app. |
| `tools[].id` | Short stable key for the app. |
| `tools[].name` | First heading line on the card, shown in capitals. |
| `tools[].subtitle` | Second heading line, shown in capitals. |
| `tools[].summary` | One sentence about the app, for an app that is not installed. |
| `tools[].package` | The app's Android application ID. Must start with `com.cyberinellc.`. |
| `tools[].published` | `true` once the app is live on Google Play. Until then the card says COMING SOON and offers no store link. |
| `tools[].counts` | The four count names on the card, used until the app is installed and hands over its own. |
| `tools[].version_name` | Optional. The newest release as shown to the user, e.g. `1.0`. |
| `tools[].version_code` | Optional. The newest release's `versionCode`. When it is greater than the installed app's code, the card says "Update ready" and offers an Update button that opens Google Play. Raise it only when that build is live on Play. |
| `tools[].model_label` | Optional. The newest model as shown to the user (Sensor Watch only). |
| `tools[].model_version` | Optional. The newest model's number, compared with the model in use (Sensor Watch only). |

Rules the apps apply: `version` must not be raised above 2 (an unknown format version is refused); every `package` must start with `com.cyberinellc.`; every text is non-empty, at most 120 characters, with no control characters; exactly four `counts`; `version_code` and `model_version` are whole numbers that are not negative. One bad entry refuses the whole file, and the apps keep the last good copy. Unknown keys are ignored.

Hosted `name`, `subtitle`, `summary` and `counts` override the apps' built-in text, so a change here shows on every card in every app at its next refresh (at most once a day; the GitHub raw host caches for about five minutes).

Adding an app to the suite means adding one entry here. Nothing changes in the apps already installed: they show the new entry on their next catalog refresh.

Copyright (c) 2026 CYBERINE LLC. All rights reserved.
