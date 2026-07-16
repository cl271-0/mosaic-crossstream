# CurseForge Integration

Last updated: 2026-07-17

## Purpose and scope

Mosaic CrossStream plans to use the official CurseForge API to provide read-only discovery and installation support for Minecraft community resources. Supported resource types may include mods, modpacks, resource packs, shader packs, and data packs.

The integration is intended to help users:

- search for Minecraft projects;
- view project metadata and compatible files;
- filter files by Minecraft version and mod loader;
- resolve declared project dependencies; and
- install files only when CurseForge provides an authorized download method.

Mosaic CrossStream uses Minecraft game ID `432`. The planned integration uses official project search, project details, project files, file details, and permitted download URL endpoints.

## Author attribution and distribution

Mosaic CrossStream is designed to preserve the connection between users, project authors, and CurseForge:

- CurseForge is clearly identified as the resource source.
- Project authorship and original project names are preserved.
- Users can open the original CurseForge project page from the launcher.
- Project files are not re-hosted by Mosaic CrossStream.
- Mosaic CrossStream does not manufacture, infer, or bypass download URLs when CurseForge does not provide an authorized download method.
- Author distribution settings and unavailable-download states are respected.
- Downloads occur only after a user requests an installation.

Mosaic CrossStream does not modify third-party project files or present them as its own content.

## API key protection

The CurseForge API key will be stored only on an MCS-controlled backend. It will not be embedded in the Windows client, included in release packages, written to client logs, committed to source control, or disclosed to end users.

The desktop client communicates with the MCS backend, and the backend performs the authorized CurseForge request. The backend applies request validation, bounded concurrency, and rate limiting to prevent misuse. It does not expose a general-purpose CurseForge proxy or return the API key to clients.

## Data handling

The integration sends only the resource query information needed to complete the user's request, such as resource type, search text, Minecraft version, mod loader, project ID, or file ID.

Mosaic CrossStream does not send Microsoft passwords, Microsoft OAuth tokens, Minecraft access tokens, or locally stored account credentials to CurseForge.

Before the integration is enabled, storage of CurseForge API responses will remain disabled unless CurseForge grants express permission for a specific caching policy. Technical processing required to complete the current request is kept in memory only for the duration necessary to serve that request.

## Downloads and dependencies

Mosaic CrossStream will use only download information returned or explicitly authorized by CurseForge. If a file cannot be downloaded through the approved API flow, the launcher will not bypass that restriction and may instead direct the user to the original project page.

Declared dependencies are resolved through official project and file metadata. A failed or unavailable dependency is reported to the user rather than silently ignored.

## Commercial status

Mosaic CrossStream is currently non-commercial. The project does not sell CurseForge API access, charge users for CurseForge downloads, or place its own advertising around CurseForge content.

If the project's business model changes, the relevant platform requirements will be reviewed before the change is introduced.

## Compliance and contact

Mosaic CrossStream will enable the CurseForge integration only after approval and will adjust its implementation in response to CurseForge review requirements, API documentation, rate limits, and author-distribution policies.

Questions about this integration can be sent to [cl271@outlook.com](mailto:cl271@outlook.com).

Official references:

- [CurseForge API documentation](https://docs.curseforge.com/rest-api/)
- [CurseForge third-party API terms and conditions](https://support.curseforge.com/support/solutions/articles/9000207405-curseforge-3rd-party-api-terms-and-conditions)
