
# E Wallet 1

*This model accepts additional fields of type array.*

## Structure

`EWallet1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fundingSource` | `?string` | Optional | Payment mode for the reference transaction.<br>Possible values:<br><br>- `INSTANT_TRANSFER`<br>- `MANUAL_BANK_TRANSFER`<br>- `DELAYED_TRANSFER`<br>- `ECHECK`<br><br>**Constraints**: *Maximum Length*: `30` | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `accountId` | `?string` | Optional | The ID of the customer, passed in the return_url field by PayPal after customer approval.<br><br>**Constraints**: *Maximum Length*: `30` | getAccountId(): ?string | setAccountId(?string accountId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet1 = EWallet1Builder::init()
    ->fundingSource('fundingSource4')
    ->accountId('accountId0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

