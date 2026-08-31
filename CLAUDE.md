# EmptyTheSeas — data

One of three repositories developed together and expected to be checked out as
siblings in the same parent directory, so relative paths between them resolve:

    <parent>/
      emptytheseas/           client   — the iOS app
      emptyseasdatapipeline/  pipeline — builds what is published here
      emptySeasDataV2/        data     — this repo

Generated output, not source. Every file here is produced by
`../emptyseasdatapipeline/bluetopo.py` and published by copying the resulting
`<slug>.pmtiles` and `<slug>.meta.json` in and pushing; GitHub Pages serves them
with range requests, which is how the client streams individual tiles. Do not
hand-edit a package — rebuild it.

Separate from the v1 `emptySeasData` repo, which the shipping v1 app still
downloads from and which must be left untouched.
