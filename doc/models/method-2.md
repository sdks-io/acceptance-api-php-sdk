
# Method 2

*This model accepts additional fields of type array.*

## Structure

`Method2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | A Payment Type is enabled through a Method. Examples: Visa, Master Card, ApplePay, iDeal, 7Eleven, alfamart, bofaPayByBank, payToPayByBank, etc<br><br>For Japan Payment Processing Valid Values:<br><br>- 1 Banking Data<br>- 2 Authorization Data<br><br>#### Via KCP<br><br>- `KCP` : Local Card, Bank Transfer and Carrier Billing.<br>- `PAYCO`<br>- `KAKAOPAY`<br>- `NAVERPAY` | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$method2 = Method2Builder::init()
    ->name('name6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

