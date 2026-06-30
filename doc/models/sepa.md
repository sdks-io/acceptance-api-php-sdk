
# Sepa

*This model accepts additional fields of type array.*

## Structure

`Sepa`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `directDebitSepa` | [`?DirectDebitSepa`](../../doc/models/direct-debit-sepa.md) | Optional | - | getDirectDebitSepa(): ?DirectDebitSepa | setDirectDebitSepa(?DirectDebitSepa directDebitSepa): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SepaBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DirectDebitSepaBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$sepa = SepaBuilder::init()
    ->directDebitSepa(
        DirectDebitSepaBuilder::init()
            ->reference('reference4')
            ->signatureDate('signatureDate4')
            ->url('url4')
            ->type('type0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

