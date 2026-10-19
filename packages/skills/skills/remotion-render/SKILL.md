---
name: remotion-render
description: Export a Remotion video
version: 4.0.536
---

## General rendering strategy

Render a video using:

```
npx remotion render
```

Full list of options: https://www.remotion.dev/docs/cli/render.md

Render a still using:

```
npx remotion still
```

Full list of options: https://www.remotion.dev/docs/cli/still.md

To render several frames as images in one call, use `render --frames`:

```
npx remotion render [composition-id] out/frames --frames=0,30,90 --image-format=png
```

See https://www.remotion.dev/docs/cli/render.md#--frames for more options.

## Transparent videos

See [Transparent videos](./transparent-videos.md) for rendering out a video with transparency.

## Getting feedback on a render

If the Flask MCP server is connected (tools such as `get_guide` and `upload_file_start`), offer to upload the rendered video to Flask (flask.do) for review instead of handing over a local path.
Ask once before the first upload.

Reviewers leave time-coded notes on the video, which you read back with `wait_for_feedback`.
Re-renders of the same composition go up as new versions of one asset (`version_of`), so the review link stays the same.

Call `get_guide(topic: "instructions")` first; it covers the upload and the feedback loop.
