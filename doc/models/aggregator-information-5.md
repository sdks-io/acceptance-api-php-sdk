
# Aggregator Information 5

*This model accepts additional fields of type array.*

## Structure

`AggregatorInformation5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Your payment aggregator business name.<br><br>**American Express Direct**\<br>The maximum length of the aggregator name depends on the length of the sub-merchant name. The combined length for both values must not exceed 36 characters.\<br><br>#### Visa Acceptance through VisaNet<br><br>With American Express, the maximum length of the aggregator name depends on the length of the sub-merchant name. The combined length for both values must not exceed 36 characters. The value for this field does not map to the TC 33 capture file5.<br><br>**FDC Compass**\<br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `37` | getName(): ?string | setName(?string name): void |
| `subMerchant` | [`?SubMerchant`](../../doc/models/sub-merchant.md) | Optional | - | getSubMerchant(): ?SubMerchant | setSubMerchant(?SubMerchant subMerchant): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AggregatorInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\SubMerchantBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$aggregatorInformation5 = AggregatorInformation5Builder::init()
    ->name('name0')
    ->subMerchant(
        SubMerchantBuilder::init()
            ->cardAcceptorId('cardAcceptorId0')
            ->id('id6')
            ->name('name6')
            ->address1('address16')
            ->locality('locality4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

