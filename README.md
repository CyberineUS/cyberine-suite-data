# cyberine-suite-data

Public data read by every CYBERINE suite app. Nothing here is personal: the files are the same for every user, and the apps send nothing when they fetch them.

## suite_catalog.json

The list of apps in the suite, shown on each app's CYBERINE Suite page.

| Field | Meaning |
|---|---|
| `version` | Format version. The apps read version 2. |
| `suite_name` | The suite's name as shown on the page. |
| `tools[].id` | Short stable key for the app. |
| `tools[].name` | First heading line on the card, shown in capitals. |
| `tools[].subtitle` | Second heading line, shown in capitals. |
| `tools[].summary` | One sentence about the app, for an app that is not installed. |
| `tools[].package` | The app's Android application ID. Must start with `com.cyberinellc.`. |
| `tools[].published` | `true` once the app is live on Google Play. Until then the card says COMING SOON and offers no store link. |
| `tools[].counts` | The four count names on the card, used until the app is installed and hands over its own. |

Adding an app to the suite means adding one entry here. Nothing changes in the apps already installed: they show the new entry on their next catalog refresh.

Copyright (c) 2026 CYBERINE LLC. All rights reserved.
