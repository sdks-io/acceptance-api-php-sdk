
# E Wallet

*This model accepts additional fields of type array.*

## Structure

`EWallet`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountId` | `?string` | Optional | The ID of the customer, passed in the return_url field by PayPal after customer approval.<br><br>**Constraints**: *Maximum Length*: `26` | getAccountId(): ?string | setAccountId(?string accountId): void |
| `fundingSource` | `?string` | Optional | Payment method for the unit purchase.<br>Possible values:<br><br>- `UNRESTRICTED (default)—this value is only available if configured by PayPal for the merchant.`<br>- `INSTANT`<br><br>**Constraints**: *Maximum Length*: `30` | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWalletBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet = EWalletBuilder::init()
    ->accountId('accountId4')
    ->fundingSource('fundingSource2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

