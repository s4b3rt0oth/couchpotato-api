# couchpotato-api

Small module which helps you query the CouchPotato HTTP API.

Please refer to the CouchPotato API documentation for further explanations and endpoints.

## Usage

**CouchPotatoAPI(options)**

Instantiate a CouchPotatoAPI client.

Options:
- **hostname**: hostname where CouchPotato runs (required)
- **apiKey**: Your API to access CouchPotato (required)
- **port**: port number CouchPotato is listening on (optional, default: 5050)
- **urlBase**: URL Base of CouchPotato (optional, default: null)
- **ssl**: Set to true if you are connecting via SSL (default: false)
- **username**: HTTP Auth username (default: null)
- **password**: HTTP Auth password (default: null)

## Methods

```js
get - send a GET request to the CouchPotato API - if available returns json
post - send a POST request to the CouchPotato API - if available returns json
```

## Examples

```js
var CouchPotatoAPI = require('couchpotato-api');

var couchpotato = new CouchPotatoAPI({
  hostname: 'localhost',
  apiKey: '(insert your API key here)',
  port: 5050,
  urlBase: '/couchpotato'
});

// get CouchPotato version
couchpotato.get("app.version").then(function (result) {
 	// result will be json a response
}).catch(function (err) {
  throw new Error("There was a error processing the request: " + err);
});
```

## Changelog

### v0.1.0
- Initial release

## License
(The MIT License)

Copyright (c) 2015 Devin Buhl &lt;devin.kray@gmail.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
