
# E Wallet 2

*This model accepts additional fields of type array.*

## Structure

`EWallet2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fundingSource` | `?string` | Optional | Payment mode for the authorization or order transaction.  INSTANT_TRANSFER  MANUAL_BANK_TRANSFER  DELAYED_TRANSFER  ECHECK  UNRESTRICTED (default)—this value is available only when configured by PayPal for the merchant. INSTANT<br><br>**Constraints**: *Maximum Length*: `30` | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet2 = EWallet2Builder::init()
    ->fundingSource('fundingSource8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

