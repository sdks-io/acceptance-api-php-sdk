
# Payment Instrument 1

*This model accepts additional fields of type array.*

## Structure

`PaymentInstrument1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `default` | `?bool` | Optional | Flag that specifies if the Payment Instrument should be made the Customers default.<br>Possible values:<br><br>- true<br>- false : (default)<br><br>**Default**: `false` | getDefault(): ?bool | setDefault(?bool default): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrument1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInstrument1 = PaymentInstrument1Builder::init()
    ->default(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

