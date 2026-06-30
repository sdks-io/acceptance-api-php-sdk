
# Account History

*This model accepts additional fields of type array.*

## Structure

`AccountHistory`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstUseOfShippingAddress` | `?bool` | Optional | Applicable when this is not a guest account. | getFirstUseOfShippingAddress(): ?bool | setFirstUseOfShippingAddress(?bool firstUseOfShippingAddress): void |
| `shippingAddressUsageDate` | `?string` | Optional | Date when the shipping address for this transaction was first used.<br>Recommended for Discover ProtectBuy.<br>If `firstUseOfShippingAddress` is false and not a guest account, then this date is entered.<br><br>**Constraints**: *Maximum Length*: `10` | getShippingAddressUsageDate(): ?string | setShippingAddressUsageDate(?string shippingAddressUsageDate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountHistoryBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$accountHistory = AccountHistoryBuilder::init()
    ->firstUseOfShippingAddress(false)
    ->shippingAddressUsageDate('shippingAddressUsageDate0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

