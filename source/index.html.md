---
title: Backend API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="Backend-API">Backend API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Backend API

Base URLs:

* <a href="https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0">https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0</a>

Email: <a href="mailto:james@serialbox.com">Support</a> 
License: <a href="http://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **X-Api-Key**, in: header. 

<h1 id="Backend-API-secured">secured</h1>

Secured calls for clients with keys

## getSerials

<a id="opIdgetSerials"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials HTTP/1.1
Host: virtserver.swaggerhub.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.get 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.get('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /serials`

*displays a list of serials*

sorts available: created_at, release_date, title
filters: published

<h3 id="getserials-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|page number|
|per_page|query|integer|false|how many items to show per page|
|sort|query|string|false|sort string, a comma separated list of fields and asc/desc|
|published|query|boolean|false|whether the serial is published|

#### Detailed descriptions

**sort**: sort string, a comma separated list of fields and asc/desc
example "created_at asc" or "created_at asc, title desc"

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "id": "string",
      "published": true,
      "title": "string",
      "short_title": "string",
      "release_date": "2018-06-12",
      "end_date": "2018-06-12",
      "slug": "string",
      "tagline": "string",
      "short_description": "string",
      "long_description": "string",
      "text": "string",
      "default_subscriber_price": 0,
      "default_episode_price": 0,
      "custom_badge_text": "string",
      "drm_restricted": true,
      "new_episodes": true,
      "mailing_list_id": "string",
      "cover_tall": "string",
      "cover_wide": "string",
      "thumb_wide": "string",
      "thumb_tall": "string",
      "updated_at": "2018-06-12T19:14:54Z",
      "created_at": "2018-06-12T19:14:54Z"
    }
  ]
}
```

<h3 id="getserials-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|serials sent|Inline|

<h3 id="getserials-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[[Serial](#schemaserial)]|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» published|boolean|true|none|none|
|»» title|string|true|none|none|
|»» short_title|string|false|none|none|
|»» release_date|string(date)|false|none|none|
|»» end_date|string(date)|false|none|none|
|»» slug|string|true|none|none|
|»» tagline|string|false|none|none|
|»» short_description|string|false|none|none|
|»» long_description|string|false|none|none|
|»» text|string|false|none|none|
|»» default_subscriber_price|integer|false|none|none|
|»» default_episode_price|integer|false|none|none|
|»» custom_badge_text|string|false|none|none|
|»» drm_restricted|boolean|false|none|none|
|»» new_episodes|boolean|false|none|none|
|»» mailing_list_id|string|false|none|none|
|»» cover_tall|string(url)|false|none|none|
|»» cover_wide|string(url)|false|none|none|
|»» thumb_wide|string(url)|false|none|none|
|»» thumb_tall|string(url)|false|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» created_at|string(date-time)|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## getSerialById

<a id="opIdgetSerialById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId} \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId} HTTP/1.1
Host: virtserver.swaggerhub.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.get 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.get('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/serials/{serialId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /serials/{serialId}`

*retrieves info about a serial*

get info about one serial

<h3 id="getserialbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|serialId|path|string(uuid)|true|Serial id to show|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": "string",
    "published": true,
    "title": "string",
    "short_title": "string",
    "release_date": "2018-06-12",
    "end_date": "2018-06-12",
    "slug": "string",
    "tagline": "string",
    "short_description": "string",
    "long_description": "string",
    "text": "string",
    "default_subscriber_price": 0,
    "default_episode_price": 0,
    "custom_badge_text": "string",
    "drm_restricted": true,
    "new_episodes": true,
    "mailing_list_id": "string",
    "cover_tall": "string",
    "cover_wide": "string",
    "thumb_wide": "string",
    "thumb_tall": "string",
    "updated_at": "2018-06-12T19:14:54Z",
    "created_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="getserialbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success; serial returned|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|serial not found|None|

<h3 id="getserialbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[Serial](#schemaserial)|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» published|boolean|true|none|none|
|»» title|string|true|none|none|
|»» short_title|string|false|none|none|
|»» release_date|string(date)|false|none|none|
|»» end_date|string(date)|false|none|none|
|»» slug|string|true|none|none|
|»» tagline|string|false|none|none|
|»» short_description|string|false|none|none|
|»» long_description|string|false|none|none|
|»» text|string|false|none|none|
|»» default_subscriber_price|integer|false|none|none|
|»» default_episode_price|integer|false|none|none|
|»» custom_badge_text|string|false|none|none|
|»» drm_restricted|boolean|false|none|none|
|»» new_episodes|boolean|false|none|none|
|»» mailing_list_id|string|false|none|none|
|»» cover_tall|string(url)|false|none|none|
|»» cover_wide|string(url)|false|none|none|
|»» thumb_wide|string(url)|false|none|none|
|»» thumb_tall|string(url)|false|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» created_at|string(date-time)|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## getEpisodes

<a id="opIdgetEpisodes"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes HTTP/1.1
Host: virtserver.swaggerhub.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.get 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.get('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /episodes`

*displays a list of episodes*

sorts available: episode_number, created_at, release_date
title

<h3 id="getepisodes-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|page number|
|per_page|query|integer|false|how many items to show per page|
|sort|query|string|false|sort string, a comma separated list of fields and asc/desc|
|season_id|query|string(uuid)|false|find episodes attached to this season|
|published|query|boolean|false|none|
|free_pilot|query|boolean|false|none|
|show_coming_soon|query|boolean|false|none|
|release_date|query|string(date-time)|false|exact match on release date of serial|
|release_date_until|query|string(date-time)|false|match <= release date|
|release_date_since|query|string(date-time)|false|match > release date|

#### Detailed descriptions

**sort**: sort string, a comma separated list of fields and asc/desc
example "created_at asc" or "created_at asc, title desc"

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "id": "string",
      "published": true,
      "season_id": "string",
      "slug": "string",
      "sku": "string",
      "tagline": "string",
      "byline": "string",
      "episode_number": 0,
      "release_date": "2018-06-12",
      "previously_on": "string",
      "free_pilot": true,
      "number_display": "string",
      "header_background_color": "string",
      "divider_color": "string",
      "subscriber_price": 0,
      "item_price": 0,
      "shortened_url": "string",
      "show_coming_soon": true,
      "pdf": "string",
      "mobi": "string",
      "epub": "string",
      "cover": "string",
      "audio": "string",
      "divider": "string",
      "body": "string",
      "created_at": "2018-06-12T19:14:54Z",
      "updated_at": "2018-06-12T19:14:54Z"
    }
  ]
}
```

<h3 id="getepisodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|episodes sent|Inline|

<h3 id="getepisodes-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[[Episode](#schemaepisode)]|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» published|boolean|false|none|none|
|»» season_id|string(uuid)|true|none|none|
|»» slug|string|false|none|none|
|»» sku|string|true|none|none|
|»» tagline|string|false|none|none|
|»» byline|string|false|none|none|
|»» episode_number|integer|true|none|none|
|»» release_date|string(date)|false|none|none|
|»» previously_on|string|false|none|none|
|»» free_pilot|boolean|false|none|none|
|»» number_display|string|false|none|none|
|»» header_background_color|string|false|none|none|
|»» divider_color|string|false|none|none|
|»» subscriber_price|integer|false|none|none|
|»» item_price|integer|false|none|none|
|»» shortened_url|string|false|none|none|
|»» show_coming_soon|boolean|false|none|none|
|»» pdf|string|false|none|none|
|»» mobi|string|false|none|none|
|»» epub|string|false|none|none|
|»» cover|string|false|none|none|
|»» audio|string|false|none|none|
|»» divider|string|false|none|none|
|»» body|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## getEpisodeById

<a id="opIdgetEpisodeById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId} \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId} HTTP/1.1
Host: virtserver.swaggerhub.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.get 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.get('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/episodes/{episodeId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /episodes/{episodeId}`

*retrieves info about a episode*

get info about one episode

<h3 id="getepisodebyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|episodeId|path|string(uuid)|true|Episode id to show|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": "string",
    "published": true,
    "season_id": "string",
    "slug": "string",
    "sku": "string",
    "tagline": "string",
    "byline": "string",
    "episode_number": 0,
    "release_date": "2018-06-12",
    "previously_on": "string",
    "free_pilot": true,
    "number_display": "string",
    "header_background_color": "string",
    "divider_color": "string",
    "subscriber_price": 0,
    "item_price": 0,
    "shortened_url": "string",
    "show_coming_soon": true,
    "pdf": "string",
    "mobi": "string",
    "epub": "string",
    "cover": "string",
    "audio": "string",
    "divider": "string",
    "body": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="getepisodebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success; episode returned|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|episode not found|None|

<h3 id="getepisodebyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[Episode](#schemaepisode)|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» published|boolean|false|none|none|
|»» season_id|string(uuid)|true|none|none|
|»» slug|string|false|none|none|
|»» sku|string|true|none|none|
|»» tagline|string|false|none|none|
|»» byline|string|false|none|none|
|»» episode_number|integer|true|none|none|
|»» release_date|string(date)|false|none|none|
|»» previously_on|string|false|none|none|
|»» free_pilot|boolean|false|none|none|
|»» number_display|string|false|none|none|
|»» header_background_color|string|false|none|none|
|»» divider_color|string|false|none|none|
|»» subscriber_price|integer|false|none|none|
|»» item_price|integer|false|none|none|
|»» shortened_url|string|false|none|none|
|»» show_coming_soon|boolean|false|none|none|
|»» pdf|string|false|none|none|
|»» mobi|string|false|none|none|
|»» epub|string|false|none|none|
|»» cover|string|false|none|none|
|»» audio|string|false|none|none|
|»» divider|string|false|none|none|
|»» body|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## addCustomer

<a id="opIdaddCustomer"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
POST https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers HTTP/1.1
Host: virtserver.swaggerhub.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "customer": {
    "id": "string",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "client_id": "string",
    "privileges": [
      "string"
    ],
    "last_activity": "2018-06-12T19:14:54Z",
    "preferred_payment_source": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.post 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.post('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /customers`

*adds a new customer*

Adds a customer to the system

> Body parameter

```json
{
  "customer": {
    "id": "string",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "client_id": "string",
    "privileges": [
      "string"
    ],
    "last_activity": "2018-06-12T19:14:54Z",
    "preferred_payment_source": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="addcustomer-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Customer to add|
|» customer|body|[Customer](#schemacustomer)|false|none|
|»» id|body|string(uuid)|true|none|
|»» email|body|string(email)|false|none|
|»» first_name|body|string|false|none|
|»» last_name|body|string|false|none|
|»» client_id|body|string|false|XXX|
|»» privileges|body|[string]|false|none|
|»» last_activity|body|string(date-time)|false|none|
|»» preferred_payment_source|body|string|false|none|
|»» created_at|body|string(date-time)|false|none|
|»» updated_at|body|string(date-time)|false|none|

> Example responses

> 201 Response

```json
{
  "data": {
    "id": "string",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "client_id": "string",
    "privileges": [
      "string"
    ],
    "last_activity": "2018-06-12T19:14:54Z",
    "preferred_payment_source": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="addcustomer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|customer created|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|invalid input, object invalid|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|an existing item already exists|None|

<h3 id="addcustomer-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[Customer](#schemacustomer)|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» email|string(email)|false|none|none|
|»» first_name|string|false|none|none|
|»» last_name|string|false|none|none|
|»» client_id|string|false|none|XXX|
|»» privileges|[string]|false|none|none|
|»» last_activity|string(date-time)|false|none|none|
|»» preferred_payment_source|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## getCustomerById

<a id="opIdgetCustomerById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId} \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId} HTTP/1.1
Host: virtserver.swaggerhub.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.get 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.get('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers/{customerId}`

*retrieves info about a customer*

get info about one customer

<h3 id="getcustomerbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|customerId|path|string(uuid)|true|Customer id to show|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": "string",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "client_id": "string",
    "privileges": [
      "string"
    ],
    "last_activity": "2018-06-12T19:14:54Z",
    "preferred_payment_source": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="getcustomerbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success; customer returned|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|customer not found|None|

<h3 id="getcustomerbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[Customer](#schemacustomer)|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» email|string(email)|false|none|none|
|»» first_name|string|false|none|none|
|»» last_name|string|false|none|none|
|»» client_id|string|false|none|XXX|
|»» privileges|[string]|false|none|none|
|»» last_activity|string(date-time)|false|none|none|
|»» preferred_payment_source|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## getCustomerPurchases

<a id="opIdgetCustomerPurchases"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases HTTP/1.1
Host: virtserver.swaggerhub.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.get 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.get('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/purchases", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers/{customerId}/purchases`

*retrieves a customer's purchases*

get a list of customer's purchases

<h3 id="getcustomerpurchases-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|customerId|path|string(uuid)|true|Customer id to show|

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "id": "string",
      "customer_id": "string",
      "product_id": "string",
      "transaction_id": "string",
      "price": 0,
      "refunded": true,
      "is_processed": true,
      "is_paid": true,
      "receipt_sent": true,
      "source": "string",
      "processor": "string",
      "description": "string",
      "created_at": "2018-06-12T19:14:54Z",
      "updated_at": "2018-06-12T19:14:54Z"
    }
  ]
}
```

<h3 id="getcustomerpurchases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success; customer returned|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|customer not found|None|

<h3 id="getcustomerpurchases-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[[Purchase](#schemapurchase)]|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» customer_id|string(uuid)|true|none|none|
|»» product_id|string(uuid)|true|none|none|
|»» transaction_id|string|false|none|none|
|»» price|integer|true|none|none|
|»» refunded|boolean|false|none|none|
|»» is_processed|boolean|false|none|none|
|»» is_paid|boolean|false|none|none|
|»» receipt_sent|boolean|false|none|none|
|»» source|string|false|none|none|
|»» processor|string|false|none|none|
|»» description|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## logCompletedPurchase

<a id="opIdlogCompletedPurchase"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
POST https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed HTTP/1.1
Host: virtserver.swaggerhub.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "customer": {
    "customer_id": "string",
    "product_id": "string",
    "price": 0,
    "source": "string",
    "description": "string",
    "created_at": "2018-06-12T19:14:54Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.post 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.post('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/customers/{customerId}/log_completed", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /customers/{customerId}/log_completed`

*posts an already completed purchase to a customer*

posts an already completed purchase to a customer

> Body parameter

```json
{
  "customer": {
    "customer_id": "string",
    "product_id": "string",
    "price": 0,
    "source": "string",
    "description": "string",
    "created_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="logcompletedpurchase-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|customerId|path|string(uuid)|true|Customer id to show|
|body|body|object|false|Customer to add|
|» customer|body|object|false|none|
|»» customer_id|body|string(uuid)|true|none|
|»» product_id|body|string(uuid)|true|none|
|»» price|body|integer|true|none|
|»» source|body|string|true|none|
|»» description|body|string|false|none|
|»» created_at|body|string(date-time)|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": "string",
    "customer_id": "string",
    "product_id": "string",
    "transaction_id": "string",
    "price": 0,
    "refunded": true,
    "is_processed": true,
    "is_paid": true,
    "receipt_sent": true,
    "source": "string",
    "processor": "string",
    "description": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="logcompletedpurchase-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success; customer returned|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|customer not found|None|

<h3 id="logcompletedpurchase-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[Purchase](#schemapurchase)|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» customer_id|string(uuid)|true|none|none|
|»» product_id|string(uuid)|true|none|none|
|»» transaction_id|string|false|none|none|
|»» price|integer|true|none|none|
|»» refunded|boolean|false|none|none|
|»» is_processed|boolean|false|none|none|
|»» is_paid|boolean|false|none|none|
|»» receipt_sent|boolean|false|none|none|
|»» source|string|false|none|none|
|»» processor|string|false|none|none|
|»» description|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## addGift

<a id="opIdaddGift"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
POST https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts HTTP/1.1
Host: virtserver.swaggerhub.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "gift": {
    "id": "string",
    "sender_id": "string",
    "recipient_id": "string",
    "recipient_name": "string",
    "recipient_email": "string",
    "redeemed": true,
    "product_id": "string",
    "sender_name": "string",
    "message": "string",
    "code": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.post 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.post('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /gifts`

*adds a new gift*

Adds a gift to the system

> Body parameter

```json
{
  "gift": {
    "id": "string",
    "sender_id": "string",
    "recipient_id": "string",
    "recipient_name": "string",
    "recipient_email": "string",
    "redeemed": true,
    "product_id": "string",
    "sender_name": "string",
    "message": "string",
    "code": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="addgift-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Gift to add|
|» gift|body|[Gift](#schemagift)|false|none|
|»» id|body|string(uuid)|true|none|
|»» sender_id|body|string(uuid)|true|none|
|»» recipient_id|body|string(uuid)|false|none|
|»» recipient_name|body|string|false|none|
|»» recipient_email|body|string|false|none|
|»» redeemed|body|boolean|false|none|
|»» product_id|body|string(uuid)|true|none|
|»» sender_name|body|string|false|none|
|»» message|body|string|false|none|
|»» code|body|string|true|none|
|»» created_at|body|string(date-time)|false|none|
|»» updated_at|body|string(date-time)|false|none|

> Example responses

> 201 Response

```json
{
  "data": {
    "id": "string",
    "sender_id": "string",
    "recipient_id": "string",
    "recipient_name": "string",
    "recipient_email": "string",
    "redeemed": true,
    "product_id": "string",
    "sender_name": "string",
    "message": "string",
    "code": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="addgift-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|gift created|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|invalid input, object invalid|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|an existing item already exists|None|

<h3 id="addgift-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[Gift](#schemagift)|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» sender_id|string(uuid)|true|none|none|
|»» recipient_id|string(uuid)|false|none|none|
|»» recipient_name|string|false|none|none|
|»» recipient_email|string|false|none|none|
|»» redeemed|boolean|false|none|none|
|»» product_id|string(uuid)|true|none|none|
|»» sender_name|string|false|none|none|
|»» message|string|false|none|none|
|»» code|string|true|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## getGiftById

<a id="opIdgetGiftById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId} \
  -H 'Accept: application/json' \
  -H 'X-Api-Key: API_KEY'

```

```http
GET https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId} HTTP/1.1
Host: virtserver.swaggerhub.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

$.ajax({
  url: 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Api-Key':'API_KEY'

};

fetch('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Api-Key' => 'API_KEY'
}

result = RestClient.get 'https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Api-Key': 'API_KEY'
}

r = requests.get('https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Api-Key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://virtserver.swaggerhub.com/Serial-Box/Asanti_SerialBox/1.0.0/gifts/{giftId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /gifts/{giftId}`

*retrieves info about a gift*

get info about one gift

<h3 id="getgiftbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|giftId|path|string(uuid)|true|Customer id to show|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": "string",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "client_id": "string",
    "privileges": [
      "string"
    ],
    "last_activity": "2018-06-12T19:14:54Z",
    "preferred_payment_source": "string",
    "created_at": "2018-06-12T19:14:54Z",
    "updated_at": "2018-06-12T19:14:54Z"
  }
}
```

<h3 id="getgiftbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success; customer returned|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|customer not found|None|

<h3 id="getgiftbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[Customer](#schemacustomer)|false|none|none|
|»» id|string(uuid)|true|none|none|
|»» email|string(email)|false|none|none|
|»» first_name|string|false|none|none|
|»» last_name|string|false|none|none|
|»» client_id|string|false|none|XXX|
|»» privileges|[string]|false|none|none|
|»» last_activity|string(date-time)|false|none|none|
|»» preferred_payment_source|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» updated_at|string(date-time)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

# Schemas

<h2 id="tocSserial">Serial</h2>

<a id="schemaserial"></a>

```json
{
  "id": "string",
  "published": true,
  "title": "string",
  "short_title": "string",
  "release_date": "2018-06-12",
  "end_date": "2018-06-12",
  "slug": "string",
  "tagline": "string",
  "short_description": "string",
  "long_description": "string",
  "text": "string",
  "default_subscriber_price": 0,
  "default_episode_price": 0,
  "custom_badge_text": "string",
  "drm_restricted": true,
  "new_episodes": true,
  "mailing_list_id": "string",
  "cover_tall": "string",
  "cover_wide": "string",
  "thumb_wide": "string",
  "thumb_tall": "string",
  "updated_at": "2018-06-12T19:14:54Z",
  "created_at": "2018-06-12T19:14:54Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|none|none|
|published|boolean|true|none|none|
|title|string|true|none|none|
|short_title|string|false|none|none|
|release_date|string(date)|false|none|none|
|end_date|string(date)|false|none|none|
|slug|string|true|none|none|
|tagline|string|false|none|none|
|short_description|string|false|none|none|
|long_description|string|false|none|none|
|text|string|false|none|none|
|default_subscriber_price|integer|false|none|none|
|default_episode_price|integer|false|none|none|
|custom_badge_text|string|false|none|none|
|drm_restricted|boolean|false|none|none|
|new_episodes|boolean|false|none|none|
|mailing_list_id|string|false|none|none|
|cover_tall|string(url)|false|none|none|
|cover_wide|string(url)|false|none|none|
|thumb_wide|string(url)|false|none|none|
|thumb_tall|string(url)|false|none|none|
|updated_at|string(date-time)|true|none|none|
|created_at|string(date-time)|true|none|none|

<h2 id="tocSseason">Season</h2>

<a id="schemaseason"></a>

```json
{
  "id": "string",
  "title": "string",
  "slug": "string",
  "serial_id": "string",
  "season_number": 0,
  "description": "string",
  "featured": true,
  "recommended_season_id": "string",
  "sku": "string",
  "cover_tall": "string",
  "cover_wide": "string",
  "updated_at": "2018-06-12T19:14:54Z",
  "created_at": "2018-06-12T19:14:54Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|none|none|
|title|string|true|none|none|
|slug|string|true|none|none|
|serial_id|string(uuid)|false|none|none|
|season_number|integer|true|none|none|
|description|string|false|none|none|
|featured|boolean|false|none|none|
|recommended_season_id|string(uuid)|false|none|none|
|sku|string|false|none|none|
|cover_tall|string(url)|false|none|none|
|cover_wide|string(url)|false|none|none|
|updated_at|string(date-time)|true|none|none|
|created_at|string(date-time)|true|none|none|

<h2 id="tocSepisode">Episode</h2>

<a id="schemaepisode"></a>

```json
{
  "id": "string",
  "published": true,
  "season_id": "string",
  "slug": "string",
  "sku": "string",
  "tagline": "string",
  "byline": "string",
  "episode_number": 0,
  "release_date": "2018-06-12",
  "previously_on": "string",
  "free_pilot": true,
  "number_display": "string",
  "header_background_color": "string",
  "divider_color": "string",
  "subscriber_price": 0,
  "item_price": 0,
  "shortened_url": "string",
  "show_coming_soon": true,
  "pdf": "string",
  "mobi": "string",
  "epub": "string",
  "cover": "string",
  "audio": "string",
  "divider": "string",
  "body": "string",
  "created_at": "2018-06-12T19:14:54Z",
  "updated_at": "2018-06-12T19:14:54Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|none|none|
|published|boolean|false|none|none|
|season_id|string(uuid)|true|none|none|
|slug|string|false|none|none|
|sku|string|true|none|none|
|tagline|string|false|none|none|
|byline|string|false|none|none|
|episode_number|integer|true|none|none|
|release_date|string(date)|false|none|none|
|previously_on|string|false|none|none|
|free_pilot|boolean|false|none|none|
|number_display|string|false|none|none|
|header_background_color|string|false|none|none|
|divider_color|string|false|none|none|
|subscriber_price|integer|false|none|none|
|item_price|integer|false|none|none|
|shortened_url|string|false|none|none|
|show_coming_soon|boolean|false|none|none|
|pdf|string|false|none|none|
|mobi|string|false|none|none|
|epub|string|false|none|none|
|cover|string|false|none|none|
|audio|string|false|none|none|
|divider|string|false|none|none|
|body|string|false|none|none|
|created_at|string(date-time)|false|none|none|
|updated_at|string(date-time)|false|none|none|

<h2 id="tocSgift">Gift</h2>

<a id="schemagift"></a>

```json
{
  "id": "string",
  "sender_id": "string",
  "recipient_id": "string",
  "recipient_name": "string",
  "recipient_email": "string",
  "redeemed": true,
  "product_id": "string",
  "sender_name": "string",
  "message": "string",
  "code": "string",
  "created_at": "2018-06-12T19:14:54Z",
  "updated_at": "2018-06-12T19:14:54Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|none|none|
|sender_id|string(uuid)|true|none|none|
|recipient_id|string(uuid)|false|none|none|
|recipient_name|string|false|none|none|
|recipient_email|string|false|none|none|
|redeemed|boolean|false|none|none|
|product_id|string(uuid)|true|none|none|
|sender_name|string|false|none|none|
|message|string|false|none|none|
|code|string|true|none|none|
|created_at|string(date-time)|false|none|none|
|updated_at|string(date-time)|false|none|none|

<h2 id="tocSpurchase">Purchase</h2>

<a id="schemapurchase"></a>

```json
{
  "id": "string",
  "customer_id": "string",
  "product_id": "string",
  "transaction_id": "string",
  "price": 0,
  "refunded": true,
  "is_processed": true,
  "is_paid": true,
  "receipt_sent": true,
  "source": "string",
  "processor": "string",
  "description": "string",
  "created_at": "2018-06-12T19:14:54Z",
  "updated_at": "2018-06-12T19:14:54Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|none|none|
|customer_id|string(uuid)|true|none|none|
|product_id|string(uuid)|true|none|none|
|transaction_id|string|false|none|none|
|price|integer|true|none|none|
|refunded|boolean|false|none|none|
|is_processed|boolean|false|none|none|
|is_paid|boolean|false|none|none|
|receipt_sent|boolean|false|none|none|
|source|string|false|none|none|
|processor|string|false|none|none|
|description|string|false|none|none|
|created_at|string(date-time)|false|none|none|
|updated_at|string(date-time)|false|none|none|

<h2 id="tocScustomer">Customer</h2>

<a id="schemacustomer"></a>

```json
{
  "id": "string",
  "email": "user@example.com",
  "first_name": "string",
  "last_name": "string",
  "client_id": "string",
  "privileges": [
    "string"
  ],
  "last_activity": "2018-06-12T19:14:54Z",
  "preferred_payment_source": "string",
  "created_at": "2018-06-12T19:14:54Z",
  "updated_at": "2018-06-12T19:14:54Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|none|none|
|email|string(email)|false|none|none|
|first_name|string|false|none|none|
|last_name|string|false|none|none|
|client_id|string|false|none|XXX|
|privileges|[string]|false|none|none|
|last_activity|string(date-time)|false|none|none|
|preferred_payment_source|string|false|none|none|
|created_at|string(date-time)|false|none|none|
|updated_at|string(date-time)|false|none|none|

