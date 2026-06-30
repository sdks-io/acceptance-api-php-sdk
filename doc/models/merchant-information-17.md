
# Merchant Information 17

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation17`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor11`](../../doc/models/merchant-descriptor-11.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor11 | setMerchantDescriptor(?MerchantDescriptor11 merchantDescriptor): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation17Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor11Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation17 = MerchantInformation17Builder::init()
    ->merchantDescriptor(
        MerchantDescriptor11Builder::init()
            ->name('name2')
            ->email('email4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

