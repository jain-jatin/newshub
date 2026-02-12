# NewsHub Requirements Snapshot

This repository currently only contains project metadata.

To preserve the latest requested product behavior, this document captures the agreed UI/backend requirements for the News Feed and RSS integration.

## News feed data source
- News displayed in **News Shorts** and headline cards must come **only** from configured RSS feeds.
- RSS sources should be limited to feeds that are enabled in the RSS Feeds tab.
- Combine all enabled feeds into a single aggregated list.
- Deduplicate stories by canonical article URL.

## Default loading behavior
- On first NewsHub app load, News Feed should auto-fetch stories.
- Do not re-fetch just because users switch tabs.
- Loading spinner should stop once initial data is available.
- If at least one feed returns stories, render those immediately and merge late responses incrementally.

## Sorting and pagination
- Default sort order: newest to oldest.
- Pagination size: 20 cards per page.
- Pagination controls: first (`<<`), previous (`<`), page numbers, next (`>`), last (`>>`).
- Apply filters before paginating.

## Filtering
- Topics input should live in News Feed tab and support:
  - free-text entry
  - press Enter to add tag
  - removable tags with an `x`
- Filter currently loaded cards first.
- If filtered result count is below 20, fetch additional feed items and continue filtering until page fills or feeds are exhausted.

## News Shorts card UX
- Rename "Deep Dives" heading to **News Shorts**.
- Remove the blue "Deep Dive" badge from cards.
- Keep "Read full article" linking to the real article URL (not XML feed URL).
- Place Save action at lower-right after article link.
- Deep Dive action must open substantial condensed content (~50-70% of original) instead of a placeholder.

## RSS tab UX
- Remove back button from top-right of RSS Feeds page.
- Add feed logs with success/failure details to diagnose failed fetches.

## Refresh controls
- Remove redundant refresh button near sort.
- Keep one compact refresh icon control.
- Do not keep refresh/loading animation spinning after stories are loaded.
