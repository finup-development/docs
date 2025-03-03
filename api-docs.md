---
title: FinUp Wallet v1.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="finup-wallet">Finup</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

API Documentation for Finup

Base URLs:

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="finup-wallet-account">Account</h1>

## AccountController_getAccountPayments

<a id="opIdAccountController_getAccountPayments"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /accounts/{account_id}/transactions \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /accounts/{account_id}/transactions HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "filters": {
    "side": [
      "string"
    ],
    "type": [
      "string"
    ],
    "status": [
      "string"
    ],
    "source_id": "string",
    "search": "string",
    "from_created_at": "string",
    "to_created_at": "string",
    "timezone": "string"
  },
  "pagination": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/accounts/{account_id}/transactions',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/accounts/{account_id}/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/accounts/{account_id}/transactions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/accounts/{account_id}/transactions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accounts/{account_id}/transactions");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/accounts/{account_id}/transactions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /accounts/{account_id}/transactions`

*Get account payments*

> Body parameter

```json
{
  "filters": {
    "side": [
      "string"
    ],
    "type": [
      "string"
    ],
    "status": [
      "string"
    ],
    "source_id": "string",
    "search": "string",
    "from_created_at": "string",
    "to_created_at": "string",
    "timezone": "string"
  },
  "pagination": {}
}
```

<h3 id="accountcontroller_getaccountpayments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Id of account|
|x-api-key|header|string|true|API key for authentication|
|body|body|[GetAccountPaymentsDto](#schemagetaccountpaymentsdto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": [
    {
      "id": "65fc4e136fb5c06281ac5e4e",
      "account_id": "622c22cf766d7a2c1fafe2d6",
      "source_id": "65fc31cf766d7a2c1fafe2e3",
      "source": "Wallet",
      "status": "Approved",
      "side": "Credit",
      "amount": 150,
      "currency": "USD",
      "type": "ExternalTransfer",
      "created_at": "2024-03-21T15:11:15.052Z",
      "updated_at": "2024-09-05T23:53:41.885Z",
      "source_identifier": "USD2156306518",
      "external_transfer_data": {
        "payment_method": "65e73213018090468561a60c",
        "external_transfer_id": "65fc4e11895eacd8b005e71c",
        "sub_type": "External",
        "hash": "0x43b4501753829064ecee79b48c9cc94f16da2b2858b3fc4d0ea682d75ada579",
        "address_to": "0x41196b2hd983A909a84837A311639cdf57E9f"
      }
    }
  ]
}
```

<h3 id="accountcontroller_getaccountpayments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|Inline|

<h3 id="accountcontroller_getaccountpayments-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## AccountController_getAccount

<a id="opIdAccountController_getAccount"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /accounts/{account_id} \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /accounts/{account_id} HTTP/1.1

Accept: application/json
x-api-key: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/accounts/{account_id}',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/accounts/{account_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/accounts/{account_id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/accounts/{account_id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accounts/{account_id}");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/accounts/{account_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /accounts/{account_id}`

*Get specify account by id*

<h3 id="accountcontroller_getaccount-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Id of account|
|x-api-key|header|string|true|API key for authentication|

> Example responses

> 201 Response

```json
{
  "result": {
    "id": "65ac22cf346d7a2c1fafe2d6",
    "name": "FT I BOGDAN",
    "member_id": "65fc3211124d7a2c1fafecc1",
    "finup_id": "1987516235",
    "decline_rate": 0,
    "fees": {
      "deposit_fee": 0.03,
      "universal_issuing_fee": 3,
      "universal_decline_fee": 0.025,
      "transaction_fee": 0,
      "universal_transaction_fee": 0,
      "universal_deposit_fee": 0,
      "universal_withdraw_fee": 0,
      "platinum_issuing_fee": 0,
      "platinum_decline_fee": 0,
      "platinum_transaction_fee": 0,
      "platinum_deposit_fee": 0,
      "platinum_withdraw_fee": 0,
      "platinum_monthly_fee": 0
    },
    "wallet_balance": 0,
    "verification_status": "Allowed",
    "card_balance": 5
  }
}
```

<h3 id="accountcontroller_getaccount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|Inline|

<h3 id="accountcontroller_getaccount-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## AccountController_getAllAccounts

<a id="opIdAccountController_getAllAccounts"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /accounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /accounts HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "pagination": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/accounts',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/accounts', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/accounts', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accounts");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/accounts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /accounts`

*Get all accounts by user*

> Body parameter

```json
{
  "pagination": {}
}
```

<h3 id="accountcontroller_getallaccounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-api-key|header|string|true|API key for authentication|
|body|body|[GetAccountsDto](#schemagetaccountsdto)|true|Accounts body|

> Example responses

> 201 Response

```json
{
  "result": {
    "own_accounts": [
      {
        "id": "67fc3d0a766d7a2c1fafefb8",
        "created_at": "2024-04-15T10:12:24.805Z",
        "updated_at": "2025-03-05T14:22:50.900Z",
        "company": "67fc3d0a766d7a2c1fafefb2",
        "finup_id": "8527419632",
        "name": "Example Account",
        "status": "Disabled",
        "owner": "67fc3d09766d7a2c1fafefbb",
        "platinum_card_limit": 15,
        "universal_card_limit": 20,
        "fees": {
          "deposit_fee": 0.05,
          "universal_issuing_fee": 4,
          "universal_decline_fee": 0.03,
          "transaction_fee": 0.01,
          "universal_transaction_fee": 0.01,
          "universal_deposit_fee": 0.01,
          "universal_withdraw_fee": 0.01,
          "platinum_issuing_fee": 0.02,
          "platinum_decline_fee": 0.02,
          "platinum_transaction_fee": 0.01,
          "platinum_deposit_fee": 0.01,
          "platinum_withdraw_fee": 0.01,
          "platinum_monthly_fee": 0.02
        },
        "used_promocodes": []
      }
    ],
    "invited_accounts": [
      {
        "id": "67fc22cf766d7a2c1fafe3d7",
        "created_at": "2024-04-15T09:04:29.231Z",
        "updated_at": "2025-03-05T14:22:51.310Z",
        "company": "67e8861ea998a71873c84568",
        "finup_id": "7483920156",
        "name": "Example User",
        "status": "Disabled",
        "decline_rate": 0.05,
        "owner": "67e8861da998a71873c84579",
        "platinum_card_limit": 12,
        "universal_card_limit": 18,
        "fees": {
          "deposit_fee": 0.04,
          "universal_issuing_fee": 5,
          "universal_decline_fee": 0.03,
          "transaction_fee": 0.02,
          "universal_transaction_fee": 0.02,
          "universal_deposit_fee": 0.02,
          "universal_withdraw_fee": 0.02,
          "platinum_issuing_fee": 0.03,
          "platinum_decline_fee": 0.03,
          "platinum_transaction_fee": 0.02,
          "platinum_deposit_fee": 0.02,
          "platinum_withdraw_fee": 0.02,
          "platinum_monthly_fee": 0.03
        },
        "used_promocodes": []
      }
    ]
  }
}
```

<h3 id="accountcontroller_getallaccounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

<h3 id="accountcontroller_getallaccounts-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## AccountController_getCardTypes

<a id="opIdAccountController_getCardTypes"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /accounts/{account_id}/bins \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /accounts/{account_id}/bins HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/accounts/{account_id}/bins',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/accounts/{account_id}/bins',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/accounts/{account_id}/bins', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/accounts/{account_id}/bins', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accounts/{account_id}/bins");
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/accounts/{account_id}/bins", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /accounts/{account_id}/bins`

*Get Card Types by Account*

<h3 id="accountcontroller_getcardtypes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Id of account|

> Example responses

> 201 Response

```json
{
  "result": [
    {
      "id": "6705952d3ec949063b9241a0",
      "status": "Active",
      "BIN": "505849",
      "category": "Platinum || Universal",
      "currency": "USD",
      "3ds": true,
      "digital_wallet": true,
      "address": "1234 Elm St, San Francisco, CA, 94016, US"
    }
  ]
}
```

<h3 id="accountcontroller_getcardtypes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|Inline|

<h3 id="accountcontroller_getcardtypes-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## AccountController_getAccountWallets

<a id="opIdAccountController_getAccountWallets"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /accounts/{account_id}/wallets \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /accounts/{account_id}/wallets HTTP/1.1

Accept: application/json
x-api-key: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/accounts/{account_id}/wallets',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/accounts/{account_id}/wallets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/accounts/{account_id}/wallets', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/accounts/{account_id}/wallets', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accounts/{account_id}/wallets");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/accounts/{account_id}/wallets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /accounts/{account_id}/wallets`

*Get account wallets*

<h3 id="accountcontroller_getaccountwallets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Mongo ID of the account|
|x-api-key|header|string|true|API key for authentication|

> Example responses

> 201 Response

```json
{
  "result": {
    "id": "67b312e30a4c3db1b01a36e4",
    "balance": 679,
    "cards_balance": 123,
    "finup_id": "USD2265302894",
    "currency": "USD"
  }
}
```

<h3 id="accountcontroller_getaccountwallets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|Inline|

<h3 id="accountcontroller_getaccountwallets-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

<h1 id="finup-wallet-card">Card</h1>

## CardController_cardDeposit

<a id="opIdCardController_cardDeposit"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /card/{card_id}/deposit \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /card/{card_id}/deposit HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "amount": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/card/{card_id}/deposit',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/card/{card_id}/deposit',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/card/{card_id}/deposit', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/card/{card_id}/deposit', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/card/{card_id}/deposit");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/card/{card_id}/deposit", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /card/{card_id}/deposit`

*Card deposit*

> Body parameter

```json
{
  "amount": 0
}
```

<h3 id="cardcontroller_carddeposit-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|card_id|path|any|true|Mongo ID of the card|
|x-api-key|header|string|true|API key for authentication|
|body|body|[CardDepositDto](#schemacarddepositdto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": {
    "status": "SUCCESS",
    "code": 201
  }
}
```

<h3 id="cardcontroller_carddeposit-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|Inline|
|418|[I'm a teapot](https://tools.ietf.org/html/rfc2324#section-2.3.1)|none|Inline|
|420|Unknown|none|Inline|

<h3 id="cardcontroller_carddeposit-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## CardController_cardWithdraw

<a id="opIdCardController_cardWithdraw"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /card/{card_id}/withdraw \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /card/{card_id}/withdraw HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "amount": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/card/{card_id}/withdraw',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/card/{card_id}/withdraw',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/card/{card_id}/withdraw', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/card/{card_id}/withdraw', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/card/{card_id}/withdraw");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/card/{card_id}/withdraw", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /card/{card_id}/withdraw`

*Card withdraw*

> Body parameter

```json
{
  "amount": 0
}
```

<h3 id="cardcontroller_cardwithdraw-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|card_id|path|any|true|Mongo ID of the card|
|x-api-key|header|string|true|API key for authentication|
|body|body|[CardWithdrawDto](#schemacardwithdrawdto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": {
    "status": "SUCCESS",
    "code": 201
  }
}
```

<h3 id="cardcontroller_cardwithdraw-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|Inline|
|418|[I'm a teapot](https://tools.ietf.org/html/rfc2324#section-2.3.1)|none|Inline|
|420|Unknown|none|Inline|

<h3 id="cardcontroller_cardwithdraw-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## CardController_issueCardsV2

<a id="opIdCardController_issueCardsV2"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /accounts/{account_id}/cards/issuing \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /accounts/{account_id}/cards/issuing HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "bin_id": "string",
  "name": "string",
  "notes": "string",
  "amount": 0,
  "promo": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/accounts/{account_id}/cards/issuing',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/accounts/{account_id}/cards/issuing',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/accounts/{account_id}/cards/issuing', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/accounts/{account_id}/cards/issuing', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accounts/{account_id}/cards/issuing");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/accounts/{account_id}/cards/issuing", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /accounts/{account_id}/cards/issuing`

*Issue cards*

> Body parameter

```json
{
  "bin_id": "string",
  "name": "string",
  "notes": "string",
  "amount": 0,
  "promo": "string"
}
```

<h3 id="cardcontroller_issuecardsv2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Id of account|
|x-api-key|header|string|true|API key for authentication|
|body|body|[IssueCardsDto](#schemaissuecardsdto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": [
    {
      "id": "67b37ed1be539510101fde99",
      "created_at": "2025-02-17T18:24:17.653Z",
      "updated_at": "2025-02-17T18:24:17.653Z",
      "user": "65fc3d09766d7a2c1fafef99",
      "account": "67b300e30a4c3db1b01a3699",
      "currency": "USD",
      "EXP": "**/**",
      "masked_PAN": "4559 88** **** ****",
      "finup_id": "CRD643348276",
      "name": "Approved",
      "notes": "Debit",
      "category": "Universal",
      "currency_short_name": "USD",
      "balance": 0,
      "past_balance": 0,
      "future_balance": 0,
      "deposit": 0,
      "withdraw": 0,
      "spent": 0,
      "status": "Processing",
      "bin_id": "67ade1eef9f79c20b4e78899",
      "3ds": false,
      "address": "2381 Zanker Rd Ste 110, San Jose, CA, 95131, US"
    }
  ]
}
```

<h3 id="cardcontroller_issuecardsv2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|Inline|
|420|Unknown|none|Inline|

<h3 id="cardcontroller_issuecardsv2-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## CardController_suspendCards

<a id="opIdCardController_suspendCards"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /cards/freeze \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH /cards/freeze HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "card_ids": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/cards/freeze',
{
  method: 'PATCH',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch '/cards/freeze',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('/cards/freeze', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/cards/freeze', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cards/freeze");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/cards/freeze", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /cards/freeze`

*Suspend cards by support/admin*

> Body parameter

```json
{
  "card_ids": [
    "string"
  ]
}
```

<h3 id="cardcontroller_suspendcards-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-api-key|header|string|true|API key for authentication|
|body|body|[BlockCardDto](#schemablockcarddto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": {
    "Changed cards": [
      "67c48f6fc8614632e0b338fc",
      "67c48f6fc8614632e0b998fc"
    ],
    "Unchanged cards due to inappropriate status": [
      "67c48f6fc8614632e0b558fc"
    ]
  }
}
```

<h3 id="cardcontroller_suspendcards-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

<h3 id="cardcontroller_suspendcards-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## CardController_resumeCard

<a id="opIdCardController_resumeCard"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /cards/unfreeze \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH /cards/unfreeze HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "card_ids": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/cards/unfreeze',
{
  method: 'PATCH',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch '/cards/unfreeze',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('/cards/unfreeze', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/cards/unfreeze', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cards/unfreeze");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/cards/unfreeze", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /cards/unfreeze`

*Resume cards*

> Body parameter

```json
{
  "card_ids": [
    "string"
  ]
}
```

<h3 id="cardcontroller_resumecard-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-api-key|header|string|true|API key for authentication|
|body|body|[BlockCardDto](#schemablockcarddto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": {
    "Changed cards": [
      "67c48f6fc8614632e0b338fc",
      "67c48f6fc8614632e0b998fc"
    ],
    "Unchanged cards due to inappropriate status": [
      "67c48f6fc8614632e0b558fc"
    ]
  }
}
```

<h3 id="cardcontroller_resumecard-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

<h3 id="cardcontroller_resumecard-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## CardController_canselCard

<a id="opIdCardController_canselCard"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /cards/close \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH /cards/close HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "card_ids": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/cards/close',
{
  method: 'PATCH',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch '/cards/close',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('/cards/close', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/cards/close', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cards/close");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/cards/close", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /cards/close`

*Cancel cards*

> Body parameter

```json
{
  "card_ids": [
    "string"
  ]
}
```

<h3 id="cardcontroller_canselcard-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-api-key|header|string|true|API key for authentication|
|body|body|[BlockCardDto](#schemablockcarddto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": {
    "Changed cards": [
      "67c48f6fc8614632e0b338fc",
      "67c48f6fc8614632e0b998fc"
    ],
    "Unchanged cards due to inappropriate status": [
      "67c48f6fc8614632e0b558fc"
    ]
  }
}
```

<h3 id="cardcontroller_canselcard-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

<h3 id="cardcontroller_canselcard-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## CardController_getAccountCards

<a id="opIdCardController_getAccountCards"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /accounts/{account_id}/cards \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /accounts/{account_id}/cards HTTP/1.1

Content-Type: application/json
Accept: application/json
x-api-key: string

```

```javascript
const inputBody = '{
  "filters": {
    "bin": [
      "string"
    ],
    "status": "[\"Enabled\", \"Canceled\"]",
    "currency": [
      "string"
    ],
    "category": [
      "string"
    ],
    "balance_from": 0,
    "balance_to": 0,
    "search": "string"
  },
  "pagination": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/accounts/{account_id}/cards',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/accounts/{account_id}/cards',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/accounts/{account_id}/cards', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/accounts/{account_id}/cards', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accounts/{account_id}/cards");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/accounts/{account_id}/cards", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /accounts/{account_id}/cards`

*Get account cards*

> Body parameter

```json
{
  "filters": {
    "bin": [
      "string"
    ],
    "status": "[\"Enabled\", \"Canceled\"]",
    "currency": [
      "string"
    ],
    "category": [
      "string"
    ],
    "balance_from": 0,
    "balance_to": 0,
    "search": "string"
  },
  "pagination": {}
}
```

<h3 id="cardcontroller_getaccountcards-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Id of account|
|x-api-key|header|string|true|API key for authentication|
|body|body|[GetCardsDto](#schemagetcardsdto)|true|Body|

> Example responses

> 201 Response

```json
{
  "result": {
    "id": "67c48f6fc8614632e0b338fc",
    "name": "Approved",
    "bin_id": "67bcf2abf8e89d31c5f8995e",
    "notes": "Credit",
    "status": "Pending",
    "user": "67aa1b2c3d4e5f6789abcdef",
    "EXP": "**/**",
    "account": "67c401f9a5b7cde210f44567",
    "balance": 50,
    "deposit": 1000,
    "withdraw": 500,
    "spent": 450,
    "masked_PAN": "1234 56•• •••• ••••",
    "currency": "EUR",
    "category": "Business",
    "created_at": "2025-03-21T14:30:10.123Z",
    "past_balance": 75,
    "future_balance": 125
  }
}
```

<h3 id="cardcontroller_getaccountcards-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

<h3 id="cardcontroller_getaccountcards-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## CardController_getAccountCard

<a id="opIdCardController_getAccountCard"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /cards/{card_id} \
  -H 'Accept: application/json' \
  -H 'x-api-key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /cards/{card_id} HTTP/1.1

Accept: application/json
x-api-key: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('/cards/{card_id}',
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
  'x-api-key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/cards/{card_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/cards/{card_id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'string',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/cards/{card_id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cards/{card_id}");
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
        "x-api-key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/cards/{card_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /cards/{card_id}`

*Get specified account card*

<h3 id="cardcontroller_getaccountcard-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|card_id|path|string|true|Mongo ID of the card|
|x-api-key|header|string|true|API key for authentication|

> Example responses

> 201 Response

```json
{
  "result": {
    "id": "67aa1234567890abcdef1234",
    "created_at": "2025-01-15T10:30:45.123Z",
    "updated_at": "2025-06-20T16:45:30.789Z",
    "member": "67bb0987654321fedcba5678",
    "user": "67cc112233445566778899aa",
    "account": "67dd2233445566778899bbaa",
    "PAN": "1234567812345678",
    "EXP": "12/30",
    "CVV": "123",
    "masked_PAN": "1234 56•• •••• 5678",
    "name": "Virtual Card",
    "balance": 100,
    "deposit": 4500.5,
    "withdraw": 1200.75,
    "spent": 3300.25,
    "status": "Active",
    "currency": "USD",
    "currency_short_name": "USD",
    "future_balance": 150,
    "past_balance": 200,
    "category": "Business",
    "bin_id": "67ee33445566778899aabbcc",
    "3ds": true
  }
}
```

<h3 id="cardcontroller_getaccountcard-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|Inline|

<h3 id="cardcontroller_getaccountcard-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

# Schemas

<h2 id="tocS_GetAccountPaymentsFilters">GetAccountPaymentsFilters</h2>
<!-- backwards compatibility -->
<a id="schemagetaccountpaymentsfilters"></a>
<a id="schema_GetAccountPaymentsFilters"></a>
<a id="tocSgetaccountpaymentsfilters"></a>
<a id="tocsgetaccountpaymentsfilters"></a>

```json
{
  "side": [
    "string"
  ],
  "type": [
    "string"
  ],
  "status": [
    "string"
  ],
  "source_id": "string",
  "search": "string",
  "from_created_at": "string",
  "to_created_at": "string",
  "timezone": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|side|[string]|true|none|none|
|type|[string]|true|none|none|
|status|[string]|true|none|none|
|source_id|string|true|none|none|
|search|string|true|none|none|
|from_created_at|string|true|none|none|
|to_created_at|string|true|none|none|
|timezone|string|true|none|none|

<h2 id="tocS_PaginationV2Dto">PaginationV2Dto</h2>
<!-- backwards compatibility -->
<a id="schemapaginationv2dto"></a>
<a id="schema_PaginationV2Dto"></a>
<a id="tocSpaginationv2dto"></a>
<a id="tocspaginationv2dto"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_GetAccountPaymentsDto">GetAccountPaymentsDto</h2>
<!-- backwards compatibility -->
<a id="schemagetaccountpaymentsdto"></a>
<a id="schema_GetAccountPaymentsDto"></a>
<a id="tocSgetaccountpaymentsdto"></a>
<a id="tocsgetaccountpaymentsdto"></a>

```json
{
  "filters": {
    "side": [
      "string"
    ],
    "type": [
      "string"
    ],
    "status": [
      "string"
    ],
    "source_id": "string",
    "search": "string",
    "from_created_at": "string",
    "to_created_at": "string",
    "timezone": "string"
  },
  "pagination": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|filters|[GetAccountPaymentsFilters](#schemagetaccountpaymentsfilters)|true|none|none|
|pagination|[PaginationV2Dto](#schemapaginationv2dto)|true|none|none|

<h2 id="tocS_GetAccountsDto">GetAccountsDto</h2>
<!-- backwards compatibility -->
<a id="schemagetaccountsdto"></a>
<a id="schema_GetAccountsDto"></a>
<a id="tocSgetaccountsdto"></a>
<a id="tocsgetaccountsdto"></a>

```json
{
  "pagination": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|[PaginationV2Dto](#schemapaginationv2dto)|true|none|none|

<h2 id="tocS_CardDepositDto">CardDepositDto</h2>
<!-- backwards compatibility -->
<a id="schemacarddepositdto"></a>
<a id="schema_CardDepositDto"></a>
<a id="tocScarddepositdto"></a>
<a id="tocscarddepositdto"></a>

```json
{
  "amount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|number|true|none|none|

<h2 id="tocS_CardWithdrawDto">CardWithdrawDto</h2>
<!-- backwards compatibility -->
<a id="schemacardwithdrawdto"></a>
<a id="schema_CardWithdrawDto"></a>
<a id="tocScardwithdrawdto"></a>
<a id="tocscardwithdrawdto"></a>

```json
{
  "amount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|number|true|none|none|

<h2 id="tocS_IssueCardsDto">IssueCardsDto</h2>
<!-- backwards compatibility -->
<a id="schemaissuecardsdto"></a>
<a id="schema_IssueCardsDto"></a>
<a id="tocSissuecardsdto"></a>
<a id="tocsissuecardsdto"></a>

```json
{
  "bin_id": "string",
  "name": "string",
  "notes": "string",
  "amount": 0,
  "promo": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bin_id|string|true|none|ID of card_type|
|name|string|true|none|none|
|notes|string|true|none|none|
|amount|number|true|none|Number of cards to be created|
|promo|string|true|none|none|

<h2 id="tocS_BlockCardDto">BlockCardDto</h2>
<!-- backwards compatibility -->
<a id="schemablockcarddto"></a>
<a id="schema_BlockCardDto"></a>
<a id="tocSblockcarddto"></a>
<a id="tocsblockcarddto"></a>

```json
{
  "card_ids": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|card_ids|[string]|true|none|none|

<h2 id="tocS_GetCardsFilters">GetCardsFilters</h2>
<!-- backwards compatibility -->
<a id="schemagetcardsfilters"></a>
<a id="schema_GetCardsFilters"></a>
<a id="tocSgetcardsfilters"></a>
<a id="tocsgetcardsfilters"></a>

```json
{
  "bin": [
    "string"
  ],
  "status": "[\"Enabled\", \"Canceled\"]",
  "currency": [
    "string"
  ],
  "category": [
    "string"
  ],
  "balance_from": 0,
  "balance_to": 0,
  "search": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bin|[string]|false|none|List of allowable BINs.|
|status|[string]|false|none|none|
|currency|[string]|false|none|A list of allowable currencies. Pass the currency ID.|
|category|[string]|false|none|A list of allowable categories.|
|balance_from|number|false|none|A filtering parameter that specifies the minimum balance value. Only objects with balance exceeding this value are returned|
|balance_to|number|false|none|A filtering parameter that specifies the maximum balance value. Only objects with balance that do not exceed this value are returned|
|search|string|false|none|Parameter that searches by substring.|

<h2 id="tocS_GetCardsDto">GetCardsDto</h2>
<!-- backwards compatibility -->
<a id="schemagetcardsdto"></a>
<a id="schema_GetCardsDto"></a>
<a id="tocSgetcardsdto"></a>
<a id="tocsgetcardsdto"></a>

```json
{
  "filters": {
    "bin": [
      "string"
    ],
    "status": "[\"Enabled\", \"Canceled\"]",
    "currency": [
      "string"
    ],
    "category": [
      "string"
    ],
    "balance_from": 0,
    "balance_to": 0,
    "search": "string"
  },
  "pagination": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|filters|[GetCardsFilters](#schemagetcardsfilters)|true|none|none|
|pagination|[PaginationV2Dto](#schemapaginationv2dto)|true|none|none|

