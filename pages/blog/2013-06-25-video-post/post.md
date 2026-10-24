---
title: "A Post with a Video"
slug: video-post
description: "Custom written post descriptions are the way to go... if you're not lazy."
date: 06/25/2013
taxonomy:
    tags: [sample post, video]
video:
    youtube: SU3kYxJmWuQ
---

Video embeds are responsive and scale with the width of the main content block with the help of [FitVids](http://fitvidsjs.com/).

The video goes in the post's front matter rather than in its content. Grav 2 escapes raw `<iframe>` tags in page content, so the theme draws the player for you:

```yaml
video:
    youtube: SU3kYxJmWuQ   # or vimeo: 76979871
```
