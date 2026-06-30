
# Risk Information 3

*This model accepts additional fields of type array.*

## Structure

`RiskInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `profile` | [`?Profile3`](../../doc/models/profile-3.md) | Optional | - | getProfile(): ?Profile3 | setProfile(?Profile3 profile): void |
| `eventType` | `?string` | Optional | Specifies one of the following types of events:<br><br>- login<br>- account_creation<br>- account_update<br>  For regular payment transactions, do not send this field.<br><br>**Constraints**: *Maximum Length*: `255` | getEventType(): ?string | setEventType(?string eventType): void |
| `buyerHistory` | [`?BuyerHistory`](../../doc/models/buyer-history.md) | Optional | - | getBuyerHistory(): ?BuyerHistory | setBuyerHistory(?BuyerHistory buyerHistory): void |
| `auxiliaryData` | [`?(AuxiliaryDatum[])`](../../doc/models/auxiliary-datum.md) | Optional | - | getAuxiliaryData(): ?array | setAuxiliaryData(?array auxiliaryData): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RiskInformation3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Profile3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerHistoryBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerAccountBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountHistoryBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AuxiliaryDatumBuilder;

$riskInformation3 = RiskInformation3Builder::init()
    ->profile(
        Profile3Builder::init()
            ->name('name0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->eventType('eventType4')
    ->buyerHistory(
        BuyerHistoryBuilder::init()
            ->customerAccount(
                CustomerAccountBuilder::init()
                    ->lastChangeDate('lastChangeDate8')
                    ->creationHistory('creationHistory6')
                    ->modificationHistory('modificationHistory0')
                    ->passwordHistory('passwordHistory6')
                    ->createDate('createDate2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->accountHistory(
                AccountHistoryBuilder::init()
                    ->firstUseOfShippingAddress(false)
                    ->shippingAddressUsageDate('shippingAddressUsageDate0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->accountPurchases(26)
            ->addCardAttempts(170)
            ->priorSuspiciousActivity(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->auxiliaryData(
        [
            AuxiliaryDatumBuilder::init()
                ->key('key6')
                ->value('value8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            AuxiliaryDatumBuilder::init()
                ->key('key6')
                ->value('value8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

