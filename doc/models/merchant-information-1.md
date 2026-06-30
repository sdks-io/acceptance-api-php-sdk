
# Merchant Information 1

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantName` | `?string` | Optional | Use this field only if you are requesting payment with Payer Authentication serice together.<br><br>Your company’s name as you want it to appear to the customer in the issuing bank’s authentication form.<br>This value overrides the value specified by your merchant bank.<br><br>**Constraints**: *Maximum Length*: `25` | getMerchantName(): ?string | setMerchantName(?string merchantName): void |
| `merchantDescriptor` | [`?MerchantDescriptor1`](../../doc/models/merchant-descriptor-1.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor1 | setMerchantDescriptor(?MerchantDescriptor1 merchantDescriptor): void |
| `returnUrl` | `?string` | Optional | URL for displaying payment results to the consumer (notifications) after the transaction is processed. Usually this URL belongs to merchant and its behavior is defined by merchant<br><br>**Constraints**: *Minimum Length*: `7`, *Maximum Length*: `255` | getReturnUrl(): ?string | setReturnUrl(?string returnUrl): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation1 = MerchantInformation1Builder::init()
    ->merchantName('merchantName4')
    ->merchantDescriptor(
        MerchantDescriptor1Builder::init()
            ->storeId('storeId6')
            ->storeName('storeName4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->returnUrl('returnUrl8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

