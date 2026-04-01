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

An example of making a fetch() request with a custom user-agent is:
```js
fetch('https://github.com/', {headers: {'User-Agent': 'My Value Here'}});
```

Alternatively, an example of making a XMLHttpRequest() with a custom user-agent is:
```js
const req = new XMLHttpRequest();
req.open('GET', 'https://github.com/');
req.setRequestHeader('User-Agent', 'My Value Here');
req.send();
```

Historically, when setting the User-Agent via a fetch() request, Chromium would silently replace it with the browser's intrinsic value.
Alternatively, when setting the User-Agent via a XMLHttpRequest(), Chromium would emit an error when calling `setRequestHeader()`: `Refused to set unsafe header "User-Agent"`.

With this feature enabled, Chromium will correctly send the desired header value for either request method.

## CORS

