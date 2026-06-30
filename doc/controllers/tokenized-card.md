# Tokenized Card

```php
$tokenizedCardApi = $client->getTokenizedCardApi();
```

## Class Name

`TokenizedCardApi`

## Methods

* [Post Tokenized Card](../../doc/controllers/tokenized-card.md#post-tokenized-card)
* [Get Tokenized Card](../../doc/controllers/tokenized-card.md#get-tokenized-card)
* [Delete Tokenized Card](../../doc/controllers/tokenized-card.md#delete-tokenized-card)


# Post Tokenized Card

|  |  |  |
| --- | --- | --- |
|**Tokenized cards**<br>A Tokenized card represents a network token. Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.

```php
function postTokenizedCard(TokenizedcardRequest $body, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TokenizedcardRequest`](../../doc/models/tokenizedcard-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**200**: Returns an existing tokenized card associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PostTokenizedCardResponse`](../../doc/models/post-tokenized-card-response.md).

## Example Usage

```php
$body = TokenizedcardRequestBuilder::init()->build();

$tokenizedCardApi = $client->getTokenizedCardApi();
$apiResponse = $tokenizedCardApi->postTokenizedCard($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PostTokenizedCardResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PostTokenizedCardException1Exception`](../../doc/models/post-tokenized-card-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PostTokenizedCardException21Exception`](../../doc/models/post-tokenized-card-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`PostTokenizedCardException31Exception`](../../doc/models/post-tokenized-card-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PostTokenizedCardException41Exception`](../../doc/models/post-tokenized-card-exception-41-exception.md) |
| 500 | Unexpected error. | [`PostTokenizedCardException51Exception`](../../doc/models/post-tokenized-card-exception-51-exception.md) |


# Get Tokenized Card

|  |  |  |
| --- | --- | --- |
|**Tokenized Cards**<br>A Tokenized Card represents a network token.
Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.

```php
function getTokenizedCard(string $tokenizedCardId, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tokenizedCardId` | `string` | Template, Required | The Id of a tokenized card.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**200**: Returns an existing tokenized card associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`GetTokenizedCardResponse`](../../doc/models/get-tokenized-card-response.md).

## Example Usage

```php
$tokenizedCardId = 'tokenizedCardId2';

$tokenizedCardApi = $client->getTokenizedCardApi();
$apiResponse = $tokenizedCardApi->getTokenizedCard($tokenizedCardId);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'GetTokenizedCardResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetTokenizedCardException1Exception`](../../doc/models/get-tokenized-card-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetTokenizedCardException21Exception`](../../doc/models/get-tokenized-card-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetTokenizedCardException31Exception`](../../doc/models/get-tokenized-card-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetTokenizedCardException31Exception`](../../doc/models/get-tokenized-card-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetTokenizedCardException51Exception`](../../doc/models/get-tokenized-card-exception-51-exception.md) |


# Delete Tokenized Card

|  |  |  |
| --- | --- | --- |
| The Network Token will attempt to be deleted from the card association and if successful the corresponding TMS Network Token will be deleted.

```php
function deleteTokenizedCard(string $tokenizedCardId, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tokenizedCardId` | `string` | Template, Required | The Id of a tokenized card.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**204**: The request is fulfilled but does not need to return a body

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$tokenizedCardId = 'tokenizedCardId2';

$tokenizedCardApi = $client->getTokenizedCardApi();
$apiResponse = $tokenizedCardApi->deleteTokenizedCard($tokenizedCardId);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'void:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`DeleteTokenizedCardException1Exception`](../../doc/models/delete-tokenized-card-exception-1-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`DeleteTokenizedCardException21Exception`](../../doc/models/delete-tokenized-card-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`DeleteTokenizedCardException31Exception`](../../doc/models/delete-tokenized-card-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`DeleteTokenizedCardException41Exception`](../../doc/models/delete-tokenized-card-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`DeleteTokenizedCardException21Exception`](../../doc/models/delete-tokenized-card-exception-21-exception.md) |
| 500 | Unexpected error. | [`DeleteTokenizedCardException61Exception`](../../doc/models/delete-tokenized-card-exception-61-exception.md) |

