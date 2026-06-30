
# Merchant Information 14

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor`](../../doc/models/merchant-descriptor.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor | setMerchantDescriptor(?MerchantDescriptor merchantDescriptor): void |
| `cancelUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getCancelUrl(): ?string | setCancelUrl(?string cancelUrl): void |
| `successUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getSuccessUrl(): ?string | setSuccessUrl(?string successUrl): void |
| `failureUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getFailureUrl(): ?string | setFailureUrl(?string failureUrl): void |
| `noteToBuyer` | `?string` | Optional | Free-form text field.<br><br>**Constraints**: *Maximum Length*: `25` | getNoteToBuyer(): ?string | setNoteToBuyer(?string noteToBuyer): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptorBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation14 = MerchantInformation14Builder::init()
    ->merchantDescriptor(
        MerchantDescriptorBuilder::init()
            ->name('name2')
            ->alternateName('alternateName0')
            ->contact('contact0')
            ->address1('address10')
            ->locality('locality2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->cancelUrl('cancelUrl8')
    ->successUrl('successUrl6')
    ->failureUrl('failureUrl4')
    ->noteToBuyer('noteToBuyer2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

