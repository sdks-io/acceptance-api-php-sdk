
# E Wallet 8

*This model accepts additional fields of type array.*

## Structure

`EWallet8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountId` | `?string` | Optional | The ID of the customer, passed in the return_url field by PayPal after customer approval.<br><br>**Constraints**: *Maximum Length*: `26` | getAccountId(): ?string | setAccountId(?string accountId): void |
| `fundingSource` | `?string` | Optional | Payment mode for the authorization or order transaction.  INSTANT_TRANSFER  MANUAL_BANK_TRANSFER  DELAYED_TRANSFER  ECHECK  UNRESTRICTED (default)—this value is available only when configured by PayPal for the merchant. INSTANT<br><br>**Constraints**: *Maximum Length*: `30` | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `fundingSourceSale` | `?string` | Optional | Payment method for the unit purchase.<br>Possible values:<br><br>- `UNRESTRICTED (default)—this value is only available if configured by PayPal for the merchant.`<br>- `INSTANT`<br><br>**Constraints**: *Maximum Length*: `30` | getFundingSourceSale(): ?string | setFundingSourceSale(?string fundingSourceSale): void |
| `userName` | `?string` | Optional | The Venmo user name chosen by the user, also know as a Venmo handle. | getUserName(): ?string | setUserName(?string userName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet8 = EWallet8Builder::init()
    ->accountId('accountId6')
    ->fundingSource('fundingSource0')
    ->fundingSourceSale('fundingSourceSale2')
    ->userName('userName8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

