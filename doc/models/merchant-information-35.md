
# Merchant Information 35

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation35`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor30`](../../doc/models/merchant-descriptor-30.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor30 | setMerchantDescriptor(?MerchantDescriptor30 merchantDescriptor): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation35Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor30Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation35 = MerchantInformation35Builder::init()
    ->merchantDescriptor(
        MerchantDescriptor30Builder::init()
            ->name('name2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

