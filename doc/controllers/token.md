# Token

Token resources can act on different token types such as Customers, Payment Instruments or Instrument Identifiers.

```php
$tokenApi = $client->getTokenApi();
```

## Class Name

`TokenApi`

## Methods

* [Post Token Payment Credentials](../../doc/controllers/token.md#post-token-payment-credentials)
* [Get Card Art Asset](../../doc/controllers/token.md#get-card-art-asset)


# Post Token Payment Credentials

|  |  |  |  
| --- | --- | --- |  
|**Token**<br>A Token can represent your tokenized Customer, Payment Instrument or Instrument Identifier information.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Payment Credentials**<br>Contains payment information such as the network token, generated cryptogram for Visa & MasterCard or dynamic CVV for Amex in a JSON Web Encryption (JWE) response.<br>Your system can use this API to retrieve the Payment Credentials for an existing Customer, Payment Instrument or Instrument Identifier.

```php
function postTokenPaymentCredentials(
    string $tokenId,
    PostPaymentCredentialsRequest $body,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tokenId` | `string` | Template, Required | The Id of a token representing a Customer, Payment Instrument or Instrument Identifier.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `body` | [`PostPaymentCredentialsRequest`](../../doc/models/post-payment-credentials-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**201**: A base64 encoded JSON Web Encryption (JWE) response containing encrypted Payment Credentials.

Example:
{
"kid":"a0eb65d572e556fddb68eb3a4078555605f7b283",
"cty":"json",
"typ":"JWT",
"enc":"A256GCM",
"alg":"RSA-OAEP-256"
}
[Encrypted Instrument Identifier Payment Credentials]

The encrypted Payment Credentials will contain the network token and cryptogram or dynamic CVV.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type `mixed`.

## Example Usage

```php
$tokenId = 'tokenId0';

$body = PostPaymentCredentialsRequestBuilder::init()->build();

$tokenApi = $client->getTokenApi();
$apiResponse = $tokenApi->postTokenPaymentCredentials(
    $tokenId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'mixed:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | `ApiException` |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | `ApiException` |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | `ApiException` |
| 410 | Token Not Available. The token has been deleted. | `ApiException` |
| 500 | Unexpected error. | `ApiException` |


# Get Card Art Asset

Retrieves Card Art for a specific Instrument Identifier. The Card Art is a visual representation of the cardholder's payment card.
Card Art is only available if a Network Token is successfully provisioned.

```php
function getCardArtAsset(string $instrumentIdentifierId, string $tokenProvider, string $assetType): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `instrumentIdentifierId` | `string` | Template, Required | The Id of an Instrument Identifier.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `tokenProvider` | [`string(TokenProvider1)`](../../doc/models/token-provider-1.md) | Template, Required | The token provider. |
| `assetType` | [`string(AssetType1)`](../../doc/models/asset-type-1.md) | Template, Required | The type of asset. |

## Response Type

**200**: Returns the Card Art Asset Content of a Network Token

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`GetCardArtAssetResponse`](../../doc/models/get-card-art-asset-response.md).

## Example Usage

```php
$instrumentIdentifierId = 'instrumentIdentifierId0';

$tokenProvider = TokenProvider1::AMEX;

$assetType = AssetType1::ISSUERLOGO;

$tokenApi = $client->getTokenApi();
$apiResponse = $tokenApi->getCardArtAsset(
    $instrumentIdentifierId,
    $tokenProvider,
    $assetType
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'GetCardArtAssetResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

