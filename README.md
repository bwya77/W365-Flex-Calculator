# Windows 365 Flex Calculator

[![Deploy GitHub Pages](https://github.com/bwya77/W365-Flex-Calculator/actions/workflows/pages.yml/badge.svg)](https://github.com/bwya77/W365-Flex-Calculator/actions/workflows/pages.yml)

A static calculator that explains Windows 365 Flex license-unit capacity.

## What it helps answer

- How many Flex license units are in use?
- How many shared pool or Cloud Apps Cloud PCs can still be created?
- How many dedicated Flex Cloud PCs can still be created?
- How many Flex licenses are needed when planning backward from users and peak demand?
- How does the 3 dedicated Cloud PCs per license rule work?
- Which license units are consumed by shared pools vs dedicated Cloud PCs?

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

The visual view shows each license unit as either one shared pool Cloud PC or three dedicated Cloud PC slots.

## Planning backward

Use **Plan new** when a customer knows the target users and peak demand instead of the licenses they already own.

Example:

```text
Dedicated users = 100
Dedicated users active at peak = 30
Shared users = 300
Shared users active at peak = 75
```

The calculator recommends the greater of:

```text
capacity licenses = ceiling(dedicated users / 3) + shared users active at peak
concurrency licenses = dedicated users active at peak + shared users active at peak
```

## Local use

Open `index.html` in a browser. No build step is required.

## GitHub Pages

The site deploys from `main` using GitHub Pages. After the first workflow run, enable Pages for the repository if GitHub asks you to select a source.
