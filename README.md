# Ultralytics Headless Builder

This repository contains a GitHub Action that automatically builds wheels for Ultralytics with OpenCV Headless dependency instead of the standard OpenCV.

## What it does

The GitHub Action performs the following steps:

1. Checks daily for new Ultralytics releases
2. Downloads the source code when a new release is detected
3. Replaces `opencv-python` with `opencv-python-headless` in dependency files
4. Builds wheels for the modified package
5. Creates a new release in this repository with the built wheels

## Why use this?

The standard Ultralytics package depends on `opencv-python`, which requires a GUI environment. This can cause issues in headless environments like servers or containers. By replacing it with `opencv-python-headless`, you can use Ultralytics in these environments without GUI dependencies.

## Usage

To use the modified wheels, you can download them directly from the [Releases](../../releases) page of this repository. Install them with pip:

```bash
pip install ultralytics-*.whl
```

## Manual Trigger

You can manually trigger the workflow by going to the Actions tab in the repository and selecting "Build Ultralytics Headless Wheels" workflow, then clicking "Run workflow".

## Automation

The workflow runs automatically every day at midnight UTC to check for new Ultralytics releases. 