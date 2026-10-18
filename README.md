# Experimental Blender render worker

A *public test worker only* for an A/B/A cross-repository performance experiment with `mingi201209-star/shorts-studio`.

This repository never publishes to YouTube and has no secrets, paid APIs or access to the Shorts production account.

It runs only on pushes to `render-farm/multi-20261018`. Its single job generates **three original moving 3D frames** at 320x576 Cycles6, then verifies SHA-256 of each output and uploads short-lived artifacts. Neither this image profile nor this job output can be used as the upload-quality native 1080x1920 Cycles32 footage.

Source code must be byte-identical to the coordinating repository's `benchmarks/render_farm/probe_scene.py` and `verify_probe.py`. A mismatch invalidates the experiment. Do not use `GITHUB_TOKEN` across repositories: GitHub automatically limits it to its own repository.

This experiment compares one repository rendering both shards with two repositories rendering one each, under the same owner-level GitHub Actions concurrency quota. Adding repositories does not multiply account quota.
