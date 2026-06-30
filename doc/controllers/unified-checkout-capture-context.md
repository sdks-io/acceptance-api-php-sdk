# Unified Checkout Capture Context

```php
$unifiedCheckoutCaptureContextApi = $client->getUnifiedCheckoutCaptureContextApi();
```

## Class Name

`UnifiedCheckoutCaptureContextApi`


# Generate Unified Checkout Capture Context

Unified Checkout is a powerful product within the Digital Acceptance Suite. Unified Checkout is designed to assist merchants with the adoption and inclusion of digital payments within their payment acceptance page. With Unified Checkout Integration you can add digital payment methods to create familiar, convenient and seamless payment experiences that are designed to reduce checkout friction and increase conversions.
Click to Pay Drop-in UI is built on the Unified Checkout platform.
For more information about Unified Checkout, see the [Unified Checkout Developer Guides Page]( For examples on how to integrate Unified Checkout within your webpage please see our [GitHub Unified Checkout Samples](
Generate Unified Checkout Capture Context
Generate a one-time use capture context used for the invocation of Unified Checkout. The Request wil contain all of the parameters for how Unified Checkout will operate within a client webpage. The resulting payload will be a JWT signed object that can be used to initiate Unified Checkout or Click to Pay Drop-in UI within a web page

```php
function generateUnifiedCheckoutCaptureContext(GenerateUnifiedCheckoutCaptureContextRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`GenerateUnifiedCheckoutCaptureContextRequest`](../../doc/models/generate-unified-checkout-capture-context-request.md) | Body, Required | - |

## Response Type

**201**: Capture Context Created

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type `mixed`.

## Example Usage

```php
$body = GenerateUnifiedCheckoutCaptureContextRequestBuilder::init()
    ->clientVersion('0.25')
    ->country('US')
    ->locale('en_US')
    ->build();

$unifiedCheckoutCaptureContextApi = $client->getUnifiedCheckoutCaptureContextApi();
$apiResponse = $unifiedCheckoutCaptureContextApi->generateUnifiedCheckoutCaptureContext($body);

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
| 400 | Bad Request | `ApiException` |

