
# Aggregator Information

*This model accepts additional fields of type array.*

## Structure

`AggregatorInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `aggregatorId` | `?string` | Optional | Value that identifies you as a payment aggregator. Get this value from the<br>processor.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCR6<br>- Position: 95-105<br>- Field: Payment Facilitator ID<br><br>This field is supported for Visa, Mastercard and Discover Transactions.<br><br>**FDC Compass**\<br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `20` | getAggregatorId(): ?string | setAggregatorId(?string aggregatorId): void |
| `name` | `?string` | Optional | Your payment aggregator business name.<br><br>**American Express Direct**\<br>The maximum length of the aggregator name depends on the length of the sub-merchant name. The combined length for both values must not exceed 36 characters.\<br><br>#### Visa Acceptance through VisaNet<br><br>With American Express, the maximum length of the aggregator name depends on the length of the sub-merchant name. The combined length for both values must not exceed 36 characters. The value for this field does not map to the TC 33 capture file5.<br><br>**FDC Compass**\<br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `37` | getName(): ?string | setName(?string name): void |
| `subMerchant` | [`?SubMerchant`](../../doc/models/sub-merchant.md) | Optional | - | getSubMerchant(): ?SubMerchant | setSubMerchant(?SubMerchant subMerchant): void |
| `streetAddress` | `?string` | Optional | Acquirer street name.<br><br>**Constraints**: *Maximum Length*: `150` | getStreetAddress(): ?string | setStreetAddress(?string streetAddress): void |
| `city` | `?string` | Optional | Acquirer city.<br><br>**Constraints**: *Maximum Length*: `100` | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | Acquirer state.<br><br>**Constraints**: *Maximum Length*: `10` | getState(): ?string | setState(?string state): void |
| `postalCode` | `?string` | Optional | Acquirer postal code.<br><br>**Constraints**: *Maximum Length*: `20` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Acquirer country.<br><br>**Constraints**: *Maximum Length*: `10` | getCountry(): ?string | setCountry(?string country): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AggregatorInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\SubMerchantBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$aggregatorInformation = AggregatorInformationBuilder::init()
    ->aggregatorId('aggregatorId6')
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
    ->streetAddress('streetAddress0')
    ->city('city0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

