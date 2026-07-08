# Windows 365 Flex Calculator

[![Deploy GitHub Pages](https://github.com/bwya77/W365-Flex-Calculator/actions/workflows/pages.yml/badge.svg)](https://github.com/bwya77/W365-Flex-Calculator/actions/workflows/pages.yml)

A static calculator that explains Windows 365 Flex license-unit capacity.

## What it helps answer

- How many Flex license units are in use?
- How many shared pool or Cloud Apps Cloud PCs can still be created?
- How many dedicated Flex Cloud PCs can still be created?
- How does the 3 dedicated Cloud PCs per license rule work?
- How is the active session limit different from provisioning capacity?

## Flex model used

Each Flex license can cover either:

- 1 shared pool or Cloud Apps Cloud PC
- Up to 3 dedicated Cloud PCs

The calculator uses:

```text
shared units used = shared pool Cloud PCs + Cloud Apps pool Cloud PCs
dedicated units used = ceiling(dedicated Cloud PCs / 3)
total units used = shared units used + dedicated units used
license units left = purchased licenses - total units used
```

Concurrency is separate:

```text
maximum active sessions = purchased Flex licenses
```

That means 5 Flex licenses allow at most 5 Flex Cloud PCs to have connected users at the same time. It does not mean multiple users can connect to a single Cloud PC.

## Local use

Open `index.html` in a browser. No build step is required.

## GitHub Pages

The site deploys from `main` using GitHub Pages. After the first workflow run, enable Pages for the repository if GitHub asks you to select a source.
