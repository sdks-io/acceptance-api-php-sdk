
# Payment Instrument 4

*This model accepts additional fields of type array.*

## Structure

`PaymentInstrument4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the Payment Instrument token that was created as part of a bundled TOKEN_CREATE action.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrument4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInstrument4 = PaymentInstrument4Builder::init()
    ->id('id8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

