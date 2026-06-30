
# Bank 6

*This model accepts additional fields of type array.*

## Structure

`Bank6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | [`?Account8`](../../doc/models/account-8.md) | Optional | - | getAccount(): ?Account8 | setAccount(?Account8 account): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank6 = Bank6Builder::init()
    ->account(
        Account8Builder::init()
            ->ibanSuffix('ibanSuffix8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

