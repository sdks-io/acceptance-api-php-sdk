
# Merchant Information 18

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation18`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor13`](../../doc/models/merchant-descriptor-13.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor13 | setMerchantDescriptor(?MerchantDescriptor13 merchantDescriptor): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation18Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation18 = MerchantInformation18Builder::init()
    ->merchantDescriptor(
        MerchantDescriptor13Builder::init()
            ->alternateName('alternateName0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

