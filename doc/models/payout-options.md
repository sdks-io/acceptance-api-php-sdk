
# Payout Options

*This model accepts additional fields of type array.*

## Structure

`PayoutOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `payoutInquiry` | `?string` | Optional | If true then provide attributes related to fund transfer/payouts. If payout information not found then response will have standard account lookup.<br>Possible values:<br><br>- `true`<br>- `false`<br><br>**Constraints**: *Maximum Length*: `5` | getPayoutInquiry(): ?string | setPayoutInquiry(?string payoutInquiry): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PayoutOptionsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$payoutOptions = PayoutOptionsBuilder::init()
    ->payoutInquiry('payoutInquiry8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

