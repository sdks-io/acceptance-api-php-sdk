
# E Wallet 10

*This model accepts additional fields of type array.*

## Structure

`EWallet10`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fundingSource` | `?string` | Optional | Payment mode for the transaction, possible values<br><br>- INSTANT_TRANSFER<br>- MANUAL_BANK_TRANSFER<br>- DELAYED_TRANSFER<br>- ECHECK<br><br>**Constraints**: *Maximum Length*: `24` | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet10 = EWallet10Builder::init()
    ->fundingSource('fundingSource8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

