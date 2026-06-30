
# Links 219

*This model accepts additional fields of type array.*

## Structure

`Links219`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?MSelf`](../../doc/models/m-self.md) | Optional | - | getSelf(): ?MSelf | setSelf(?MSelf self): void |
| `relatedTransactions` | [`?(RelatedTransaction[])`](../../doc/models/related-transaction.md) | Optional | - | getRelatedTransactions(): ?array | setRelatedTransactions(?array relatedTransactions): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links219Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MSelfBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\RelatedTransactionBuilder;

$links219 = Links219Builder::init()
    ->self(
        MSelfBuilder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->relatedTransactions(
        [
            RelatedTransactionBuilder::init()
                ->href('href8')
                ->method('method0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            RelatedTransactionBuilder::init()
                ->href('href8')
                ->method('method0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

