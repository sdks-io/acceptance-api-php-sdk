
# Links 14

*This model accepts additional fields of type array.*

## Structure

`Links14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactions` | [`?(Transaction[])`](../../doc/models/transaction.md) | Optional | - | getTransactions(): ?array | setTransactions(?array transactions): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TransactionBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links14 = Links14Builder::init()
    ->transactions(
        [
            TransactionBuilder::init()
                ->href('href0')
                ->method('method8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

