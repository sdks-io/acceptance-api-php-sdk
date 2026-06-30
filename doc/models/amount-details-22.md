
# Amount Details 22

*This model accepts additional fields of type array.*

## Structure

`AmountDetails22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `refundBalance` | `?string` | Optional | This field will carry the remaning amount which can be refunded.<br><br>**Constraints**: *Maximum Length*: `15` | getRefundBalance(): ?string | setRefundBalance(?string refundBalance): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails22 = AmountDetails22Builder::init()
    ->refundBalance('refundBalance6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

