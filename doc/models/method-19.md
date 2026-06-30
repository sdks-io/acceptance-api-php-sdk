
# Method 19

*This model accepts additional fields of type array.*

## Structure

`Method19`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | A Payment Type is enabled through a Method. Examples: Visa, Master Card, ApplePay, iDeal, 7Eleven, alfamart, etc<br><br>#### Via PayPal ptsV2CreateOrderPost201Response<br><br>- 'payPal'<br>- 'venmo' | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Method19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$method19 = Method19Builder::init()
    ->name('name6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

