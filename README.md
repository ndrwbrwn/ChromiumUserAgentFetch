---
title: "How to experiment with fetch() user-agents in Chrome"
maintainer: "ndrwbrwn"
created: 01/04/2026
updated: 01/04/2026
---


# How to experiment with fetch() user-agents in Chrome
In Chrome `<edit version here>`, a prototype feature is available to let the fetch() or XMLHttpRequest() APIs set or modify the User-Agent that is sent with their requests.

1. Download or update Chrome to `<edit version here>`
2. Launch Chrome with the command-line flag `--enable-features=UserAgentFollowingSpec` (See [here](https://www.chromium.org/developers/how-tos/run-chromium-with-flags/) for instructions for other platforms.)
3. Open the Chrome Devtools Console
4. Make a fetch() request with a custom user-agent

