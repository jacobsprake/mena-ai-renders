# mena-ai-renders

Public CDN for Mena AI marketing renders — covers + TwitterShots screenshots
of @trymenaai's X tweets. Fetched by Postiz via `raw.githubusercontent.com`
URLs for the IG + TikTok carousels.

## Layout

```
<YYYY-MM-DD>/
  <package-slug>/
    cover.png                ← DALL-E hero, 3:4 portrait
    ig-1080x1350/
      slide-01.png           ← cover, IG-fit
      slide-02.png           ← @trymenaai tweet 1, IG
      slide-03.png           ← @trymenaai tweet 2, IG
      ...
    tiktok-1080x1920/
      slide-01.png           ← cover, TT-letterboxed
      slide-02.png           ← @trymenaai tweet 1, TT
      ...
```

## Publishing

Auto-pushed by `mena-screenshot-x-thread` (13:00 Europe/Rome) via
[publish_to_renders_repo.py](https://github.com/jacobsprake/mena-ai/blob/main/custom-gpt/publish_to_renders_repo.py).

Manual publish:

```sh
python3 ~/mena-ai/custom-gpt/publish_to_renders_repo.py \
  --slug <package-slug> \
  --date 2026-05-28
```

Prints a JSON manifest of `https://raw.githubusercontent.com/...` URLs that
the calling SKILL passes to Postiz `integrationSchedulePostTool` as the
`attachments` array.

## Lifecycle

Old renders are kept indefinitely as a content archive — they're small
PNGs and the audit trail is useful when reviewing what went out.
