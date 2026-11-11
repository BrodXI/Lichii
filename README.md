<!--
# SPDX-FileCopyrightText: Copyright 2025 Eden Emulator Project
# SPDX-License-Identifier: GPL-3.0-or-later

# SPDX-FileCopyrightText: 2018 yuzu Emulator Project
# SPDX-License-Identifier: GPL-2.0-or-later
-->

<p align="center">
  <img src="dist/branding/lichii_icon_with_logo.png" alt="Lichii" width="600">
</p>

# Lichii: My Personal Fork

This is my **unofficial, experimental fork** of [Lichii](https://github.com/zortos293/Lichii), with my own performance, graphics, and quality-of-life tweaks. I also selectively integrate useful improvements from [Fritchii](https://github.com/Frizti/Fritchii) and other upstream work.

The focus is on testing changes that may improve real gameplay, especially on Windows and in Ocarina of Time. Performance gains and game compatibility vary by hardware, settings, and build; automated builds alone cannot guarantee an FPS increase.

## My tweaks and development approach

I experiment with CPU and Vulkan performance, shader/pipeline behavior, game-specific fixes, and usability changes. I compare changes against working builds and use automated checks where possible, followed by actual gameplay testing.

**About 10% of my personal tweaks are vibe-coded with AI assistance.** That's my rough estimate of my own changes, not a claim about the inherited emulator code. Most of the underlying project comes from the original developers and contributors credited below.

## Downloads and setup

**Download this fork only from [my GitHub Releases](https://github.com/BrodXI/Lichii/releases).** Those releases are separate from the [original Lichii releases](https://github.com/zortos293/Lichii/releases).

On Windows, extract the entire ZIP and run `lichii.exe`. If there are both standard and PGO builds, PGO is profile-guided optimization; it may help performance, but results should be compared in the same game and settings.

Back up your saves and settings before switching builds or importing a profile. Lichii normally stores its Windows data in `%APPDATA%\lichii`; a portable `user/` folder may override that location.

This project does **not** include games, firmware, or encryption keys. Use only files you have legally obtained. It is not affiliated with Nintendo or the upstream Lichii or Fritchii teams.

## Building

See the inherited [build guide](docs/Build.md), [user documentation](docs/user/README.md), and [coding guidelines](docs/Coding.md). Some documentation and internal target names still use upstream project names.

## Credits and license

This fork builds on the work of the **[original Lichii project](https://github.com/zortos293/Lichii)** and selectively incorporates ideas or code from **[Fritchii](https://github.com/Frizti/Fritchii)**. Credit also belongs to Eglantine, Eden, yuzu, Sudachi, and their contributors, including Eglantine's original developer Camille LaVey. The inherited Lichii artwork is credited to YOB (yobslab).

Original copyright notices and third-party licenses are retained. See [LICENSE.txt](LICENSE.txt) and the source files for the applicable terms.
