<h3 style="color: MediumSeaGreen;">@applaud/isomorphic-fetch</h3>
================

Fetch for node and Browserify.  Built on top of [GitHub's WHATWG Fetch polyfill](https://github.com/github/fetch).

## Warnings

- This adds `fetch` as a global so that its API is consistent between client and server.
- You must bring your own ES6 Promise compatible polyfill, I suggest [es6-promise](https://github.com/jakearchibald/es6-promise).

## Installation

### NPM

```sh
npm install --save @applaud/isomorphic-fetch
```

### Bower

```sh
bower install --save @applaud/isomorphic-fetch
```

## Usage

```js
require('es6-promise').polyfill();
require('@applaud/isomorphic-fetch');

fetch('//offline-news-api.herokuapp.com/stories')
	.then(function(response) {
		if (response.status >= 400) {
			throw new Error("Bad response from server");
		}
		return response.json();
	})
	.then(function(stories) {
		console.log(stories);
	});
```

## License

All open source code released by FT Labs is licenced under the MIT licence.  Based on [the fine work by](https://github.com/github/fetch/pull/31) **[jxck](https://github.com/Jxck)**.
