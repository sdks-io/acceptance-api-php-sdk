
# Reward Points Details

*This model accepts additional fields of type array.*

## Structure

`RewardPointsDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pointsBeforeRedemption` | `?string` | Optional | Loyalty points total balance before redemption.<br>For Example: Points, such as 100<br><br>**Constraints**: *Maximum Length*: `10` | getPointsBeforeRedemption(): ?string | setPointsBeforeRedemption(?string pointsBeforeRedemption): void |
| `pointsValueBeforeRedemption` | `?string` | Optional | The total value of loyalty points before redemption in the default currency. Max characters is 12 excluding the "." symbol<br>For Example: Points, such as 20.00<br><br>**Constraints**: *Maximum Length*: `12` | getPointsValueBeforeRedemption(): ?string | setPointsValueBeforeRedemption(?string pointsValueBeforeRedemption): void |
| `pointsRedeemed` | `?string` | Optional | Number of loyalty points that were redeemed.<br>For Example: Points, such as 100<br><br>**Constraints**: *Maximum Length*: `10` | getPointsRedeemed(): ?string | setPointsRedeemed(?string pointsRedeemed): void |
| `pointsValueRedeemed` | `?string` | Optional | The value of the loyalty points that were redeemed in the default currency. Max characters is 12 excluding the "." symbol<br>For Example: Points, such as 100.00<br><br>**Constraints**: *Maximum Length*: `12` | getPointsValueRedeemed(): ?string | setPointsValueRedeemed(?string pointsValueRedeemed): void |
| `pointsAfterRedemption` | `?string` | Optional | Loyalty Points remaining total balance after redemption.<br>For Example: Points, such as 20.00<br><br>**Constraints**: *Maximum Length*: `10` | getPointsAfterRedemption(): ?string | setPointsAfterRedemption(?string pointsAfterRedemption): void |
| `pointsValueAfterRedemption` | `?string` | Optional | The value of the remaining loyalty points after redumption in the default currency. Max characters is 12 excluding the "." symbol<br>For Example: Points, such as 20.00<br><br>**Constraints**: *Maximum Length*: `12` | getPointsValueAfterRedemption(): ?string | setPointsValueAfterRedemption(?string pointsValueAfterRedemption): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RewardPointsDetailsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$rewardPointsDetails = RewardPointsDetailsBuilder::init()
    ->pointsBeforeRedemption('pointsBeforeRedemption8')
    ->pointsValueBeforeRedemption('pointsValueBeforeRedemption0')
    ->pointsRedeemed('pointsRedeemed8')
    ->pointsValueRedeemed('pointsValueRedeemed8')
    ->pointsAfterRedemption('pointsAfterRedemption2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

