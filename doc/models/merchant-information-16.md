
# Merchant Information 16

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation16`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor11`](../../doc/models/merchant-descriptor-11.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor11 | setMerchantDescriptor(?MerchantDescriptor11 merchantDescriptor): void |
| `cancelUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getCancelUrl(): ?string | setCancelUrl(?string cancelUrl): void |
| `successUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getSuccessUrl(): ?string | setSuccessUrl(?string successUrl): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation16Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor11Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation16 = MerchantInformation16Builder::init()
    ->merchantDescriptor(
        MerchantDescriptor11Builder::init()
            ->name('name2')
            ->email('email4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->cancelUrl('cancelUrl6')
    ->successUrl('successUrl0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

