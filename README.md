# tidepool-alpha

Public render pipeline for the **AO** anime streetwear trailer (Tidepool Alpha).

- Spec: [my-file (3).txt](my-file (3).txt) — cut-by-cut trailer brief.
- Trailer length from the spec: 15s @ 24fps = 360 frames.
- Pipeline: `plan` → up to 40 `shard` jobs (each renders a frame slice of the trailer) → `join` job stitches the chunks with ffmpeg.

## Run the render

GitHub → Actions → *Render AO Trailer (Tidepool Alpha)* → **Run workflow**.

## Adding the render project

The workflow renders `Main` from `src/index.ts` (Remotion, like `KNIGHTABDO/kahf-preview-render`).
Add the render project to this repo when it exists: `package.json` + `package-lock.json`,
`src/index.ts`, `src/Main.tsx` (the `Main` composition: 1080p, 24fps, 360 frames).
Then `npm ci` in the workflow works and the shards render real slices.
