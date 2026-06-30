
# Payment Instruments 1

*This model accepts additional fields of type array.*

## Structure

`PaymentInstruments1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the Instrument Identifiers Payment Instruments. | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstruments1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInstruments1 = PaymentInstruments1Builder::init()
    ->href('tms/v1/instrumentidentifiers/7010000000016241111/paymentinstruments')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

