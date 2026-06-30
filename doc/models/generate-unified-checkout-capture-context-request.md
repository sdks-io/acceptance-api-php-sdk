
# Generate Unified Checkout Capture Context Request

*This model accepts additional fields of type array.*

## Structure

`GenerateUnifiedCheckoutCaptureContextRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientVersion` | `?string` | Optional | Specify the version of Unified Checkout that you want to use.<br><br>**Constraints**: *Maximum Length*: `60` | getClientVersion(): ?string | setClientVersion(?string clientVersion): void |
| `targetOrigins` | `?(string[])` | Optional | The [target origin]( of the website on which you will be launching Unified Checkout is defined by the scheme (protocol), hostname (domain) and port number (if used).<br><br>You must use  (unless you use<br>Wildcards are NOT supported.  Ensure that subdomains are included.<br>Any valid top-level domain is supported (e.g. .com, .co.uk, .gov.br etc)<br><br>## Examples:<br><br>- <br>- <br><br>If you are embedding within multiple nested iframes you need to specify the origins of all the browser contexts used, for example:<br><br>targetOrigins: [<br>"<br>"<br>"<br>] | getTargetOrigins(): ?array | setTargetOrigins(?array targetOrigins): void |
| `allowedCardNetworks` | `?(string[])` | Optional | The list of card networks you want to use for this Unified Checkout transaction.<br><br>Unified Checkout currently supports the following card networks:<br><br>- VISA<br>- MASTERCARD<br>- AMEX<br>- CARNET<br>- CARTESBANCAIRES<br>- CUP<br>- DINERSCLUB<br>- DISCOVER<br>- EFTPOS<br>- ELO<br>- JCB<br>- JCREW<br>- MADA<br>- MAESTRO<br>- MEEZA<br>- PAYPAK<br><br>**Constraints**: *Maximum Length*: `30` | getAllowedCardNetworks(): ?array | setAllowedCardNetworks(?array allowedCardNetworks): void |
| `allowedPaymentTypes` | `?(string[])` | Optional | The payment types that are allowed for the merchant.<br><br>Possible values when launching Unified Checkout:<br><br>- APPLEPAY<br>- CHECK<br>- CLICKTOPAY<br>- GOOGLEPAY<br>- PANENTRY<br>- PAZE <br><br><br><br>Unified Checkout also supports the following Alternative Payments:<br><br>- AFTERPAY<br><br><br><br>Possible values when launching Click To Pay Drop-In UI:<br><br>- CLICKTOPAY <br><br><br><br>**Important:**<br><br>- CLICKTOPAY only available for Visa, Mastercard and AMEX for saved cards.<br>- Visa and Mastercard will look to tokenize using network tokenization for all Click to Pay requests.  Click to Pay uses Click to Pay token requester IDs and not the merchant's existing token requester.<br>- Apple Pay, Google Pay, Check, and Paze can be used independently without requiring PAN entry in the allowedPaymentTypes field.<br><br><br><br>**Managing Google Pay Authentication Types**<br>When you enable Google Pay on Unified Checkout you can specify optional parameters that define the types of card authentication you receive from Google Pay.<br><br><br><br>**Managing Google Pay Authentication Types**<br>Where Click to Pay is the payment type selected by the customer and the customer manually enters their card, the option to enroll their card in Click to Pay will be auto-checked if this field is set to "true".<br><br>This is only available where the merchant and cardholder are based in the following countries and the billing type is set to "FULL" or "PARTIAL".<br><br>- UAE<br>- Argentina<br>- Brazil<br>- Chile<br>- Colombia<br>- Kuwait<br>- Mexico<br>- Peru<br>- Qatar<br>- Saudi Arabia<br>- Ukraine<br>- South Africa<br><br><br><br>If false, this is not present or not supported in the market.  Enrollment in Click to Pay is not checked for the customer when completing manual card entry. | getAllowedPaymentTypes(): ?array | setAllowedPaymentTypes(?array allowedPaymentTypes): void |
| `country` | `?string` | Optional | Country the purchase is originating from (e.g. country of the merchant).<br>Use the two-character ISO Standard<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `locale` | `?string` | Optional | Localization of the User experience conforming to the ISO 639-1 language standards and two-character ISO Standard Country Code.<br><br>Please refer to list of [supported locales through Unified Checkout]( | getLocale(): ?string | setLocale(?string locale): void |
| `captureMandate` | [`?CaptureMandate`](../../doc/models/capture-mandate.md) | Optional | - | getCaptureMandate(): ?CaptureMandate | setCaptureMandate(?CaptureMandate captureMandate): void |
| `completeMandate` | [`?CompleteMandate2`](../../doc/models/complete-mandate-2.md) | Optional | - | getCompleteMandate(): ?CompleteMandate2 | setCompleteMandate(?CompleteMandate2 completeMandate): void |
| `orderInformation` | [`?OrderInformation34`](../../doc/models/order-information-34.md) | Optional | - | getOrderInformation(): ?OrderInformation34 | setOrderInformation(?OrderInformation34 orderInformation): void |
| `transientTokenResponseOptions` | [`?TransientTokenResponseOptions`](../../doc/models/transient-token-response-options.md) | Optional | - | getTransientTokenResponseOptions(): ?TransientTokenResponseOptions | setTransientTokenResponseOptions(?TransientTokenResponseOptions transientTokenResponseOptions): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\GenerateUnifiedCheckoutCaptureContextRequestBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$generateUnifiedCheckoutCaptureContextRequest = GenerateUnifiedCheckoutCaptureContextRequestBuilder::init()
    ->clientVersion('0.25')
    ->targetOrigins(
        [
            'targetOrigins5',
            'targetOrigins6'
        ]
    )
    ->allowedCardNetworks(
        [
            'allowedCardNetworks6',
            'allowedCardNetworks7',
            'allowedCardNetworks8'
        ]
    )
    ->allowedPaymentTypes(
        [
            'allowedPaymentTypes6'
        ]
    )
    ->country('US')
    ->locale('en_US')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

