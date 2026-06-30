
# Transaction

*This model accepts additional fields of type array.*

## Structure

`Transaction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | Self link for this request | getHref(): ?string | setHref(?string href): void |
| `method` | `?string` | Optional | - | getMethod(): ?string | setMethod(?string method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TransactionBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$transaction = TransactionBuilder::init()
    ->href('/tss/v2/transactions/5289798134206292501013')
    ->method('method8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

