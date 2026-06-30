
# E Wallet 9

*This model accepts additional fields of type array.*

## Structure

`EWallet9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fundingSource` | `?string` | Optional | Payment method for the unit purchase.<br>Possible values:<br>UNRESTRICTED (default)—this value is<br>available only when configured by PayPal<br>for the merchant.<br>INSTANT.<br><br>**Constraints**: *Maximum Length*: `30` | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet9 = EWallet9Builder::init()
    ->fundingSource('fundingSource8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

