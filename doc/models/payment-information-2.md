
# Payment Information 2

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountFeatures` | [`?AccountFeatures1`](../../doc/models/account-features-1.md) | Optional | - | getAccountFeatures(): ?AccountFeatures1 | setAccountFeatures(?AccountFeatures1 accountFeatures): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountFeatures1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInformation2 = PaymentInformation2Builder::init()
    ->accountFeatures(
        AccountFeatures1Builder::init()
            ->category('category6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

