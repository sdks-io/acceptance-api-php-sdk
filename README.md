
# Getting Started with Visa Acceptance Merged Spec

## Introduction

All Visa Acceptance API specs merged together. These are available at https://developer.visaacceptance.com/api/reference/api-reference.html

## Install the Package

Run the following command to install the package and automatically add the dependency to your composer.json file:

```bash
composer require "visa-acceptance/acceptance-api-sdk:0.0.1"
```

Or add it to the composer.json file manually as given below:

```json
"require": {
    "visa-acceptance/acceptance-api-sdk": "0.0.1"
}
```

You can also view the package at:
https://packagist.org/packages/visa-acceptance/acceptance-api-sdk#0.0.1

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `0` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT'` |
| loggingConfiguration | [`LoggingConfigurationBuilder`](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/logging-configuration-builder.md) | Represents the logging configurations for API calls |
| proxyConfiguration | [`ProxyConfigurationBuilder`](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| bearerAuthCredentials | [`BearerAuthCredentials`](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |
| acceptCredentials | [`AcceptCredentials`](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/auth/custom-header-signature-1.md) | The Credentials Setter for Custom Header Signature |

The API client can be initialized as follows:

```php
use VisaAcceptanceMergedSpecLib\Logging\LoggingConfigurationBuilder;
use VisaAcceptanceMergedSpecLib\Logging\RequestLoggingConfigurationBuilder;
use VisaAcceptanceMergedSpecLib\Logging\ResponseLoggingConfigurationBuilder;
use Psr\Log\LogLevel;
use VisaAcceptanceMergedSpecLib\Authentication\BearerAuthCredentialsBuilder;
use VisaAcceptanceMergedSpecLib\Authentication\AcceptCredentialsBuilder;
use VisaAcceptanceMergedSpecLib\VisaAcceptanceMergedSpecClientBuilder;

$client = VisaAcceptanceMergedSpecClientBuilder::init()
    ->bearerAuthCredentials(
        BearerAuthCredentialsBuilder::init(
            'authorization'
        )
    )
    ->acceptCredentials(
        AcceptCredentialsBuilder::init(
            'Accept'
        )
    )
    ->loggingConfiguration(
        LoggingConfigurationBuilder::init()
            ->level(LogLevel::INFO)
            ->requestConfiguration(RequestLoggingConfigurationBuilder::init()->body(true))
            ->responseConfiguration(ResponseLoggingConfigurationBuilder::init()->headers(true))
    )
    ->build();
```

## Authorization

This API uses the following authentication schemes.

* [`BearerAuth (Custom Header Signature)`](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/auth/custom-header-signature.md)
* [`Accept (Custom Header Signature)`](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/auth/custom-header-signature-1.md)

## List of APIs

* [Customer Shipping Address](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/customer-shipping-address.md)
* [Customer Payment Instrument](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/customer-payment-instrument.md)
* [Payment Instrument](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/payment-instrument.md)
* [Instrument Identifier](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/instrument-identifier.md)
* [Unified Checkout Capture Context](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/unified-checkout-capture-context.md)
* [Transient Token Data](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/transient-token-data.md)
* [Tokenized Card](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/tokenized-card.md)
* [Payments](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/payments.md)
* [Capture](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/capture.md)
* [Reversal](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/reversal.md)
* [Refund](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/refund.md)
* [Credit](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/credit.md)
* [Void](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/void.md)
* [Transaction Batches](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/transaction-batches.md)
* [Billing Agreements](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/billing-agreements.md)
* [Orders](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/orders.md)
* [Payment-Tokens](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/payment-tokens.md)
* [Customer](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/customer.md)
* [Token](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/token.md)
* [Transaction Details](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/controllers/transaction-details.md)

## SDK Infrastructure

### Configuration

* [ProxyConfigurationBuilder](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/proxy-configuration-builder.md)
* [LoggingConfigurationBuilder](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/logging-configuration-builder.md)
* [RequestLoggingConfigurationBuilder](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/request-logging-configuration-builder.md)
* [ResponseLoggingConfigurationBuilder](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/response-logging-configuration-builder.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/acceptance-api-php-sdk/tree/0.0.1/doc/api-response.md)

