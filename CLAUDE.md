# EmptyTheSeas — data (LEGACY)

**Superseded. New packages are published to Cloudflare R2, not here.**

The client streams from an R2 bucket; this repo was the GitHub Pages host until
Pages' 1 GB site cap and metered bandwidth ruled it out for the national
catalogue. The copy here is stale — it predates the MLLW vertical datum shift
and the pre-contour smoothing, so its depths are NAVD88 and about a metre
deeper than chart datum.

Kept online because it costs nothing and the URL may still be referenced. Do not
publish here.

One of three repositories developed together and expected to be checked out as
siblings in the same parent directory:

    <parent>/
      emptytheseas/           client   — the iOS app
      emptyseasdatapipeline/  pipeline — builds the packages
      emptySeasDataV2/        data     — this repo, legacy

Separate again from the v1 `emptySeasData` repo, which the shipping v1 app still
downloads from and which must be left untouched.
