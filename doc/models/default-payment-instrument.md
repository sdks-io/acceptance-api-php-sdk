
# Default Payment Instrument

*This model accepts additional fields of type array.*

## Structure

`DefaultPaymentInstrument`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The Id of the Customers default Payment Instrument | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DefaultPaymentInstrumentBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$defaultPaymentInstrument = DefaultPaymentInstrumentBuilder::init()
    ->id('id4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

