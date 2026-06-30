
# Direct Debit

*This model accepts additional fields of type array.*

## Structure

`DirectDebit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mandate` | [`?Mandate`](../../doc/models/mandate.md) | Optional | - | getMandate(): ?Mandate | setMandate(?Mandate mandate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DirectDebitBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MandateBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$directDebit = DirectDebitBuilder::init()
    ->mandate(
        MandateBuilder::init()
            ->clearingDate('clearingDate6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

