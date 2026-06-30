
# Aggregator Information 1

*This model accepts additional fields of type array.*

## Structure

`AggregatorInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `aggregatorId` | `?string` | Optional | Value that identifies you as a payment aggregator. Get this value from the<br>processor.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCR6<br>- Position: 95-105<br>- Field: Payment Facilitator ID<br><br>This field is supported for Visa, Mastercard and Discover Transactions.<br><br>**FDC Compass**\<br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `20` | getAggregatorId(): ?string | setAggregatorId(?string aggregatorId): void |
| `name` | `?string` | Optional | Your payment aggregator business name.<br><br>**American Express Direct**\<br>The maximum length of the aggregator name depends on the length of the sub-merchant name. The combined length for both values must not exceed 36 characters.\<br><br>#### Visa Acceptance through VisaNet<br><br>With American Express, the maximum length of the aggregator name depends on the length of the sub-merchant name. The combined length for both values must not exceed 36 characters. The value for this field does not map to the TC 33 capture file5.<br><br>**FDC Compass**\<br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `37` | getName(): ?string | setName(?string name): void |
| `subMerchant` | [`?SubMerchant1`](../../doc/models/sub-merchant-1.md) | Optional | - | getSubMerchant(): ?SubMerchant1 | setSubMerchant(?SubMerchant1 subMerchant): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AggregatorInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\SubMerchant1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$aggregatorInformation1 = AggregatorInformation1Builder::init()
    ->aggregatorId('aggregatorId4')
    ->name('name8')
    ->subMerchant(
        SubMerchant1Builder::init()
            ->name('name6')
            ->address1('address16')
            ->locality('locality4')
            ->administrativeArea('administrativeArea2')
            ->postalCode('postalCode2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

