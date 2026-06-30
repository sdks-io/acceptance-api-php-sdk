
# Account Features 1

*This model accepts additional fields of type array.*

## Structure

`AccountFeatures1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `category` | `?string` | Optional | #### GPX<br><br>Mastercard product ID associated with the primary account number (PAN).<br>Returned by authorization service.<br><br>#### Visa Acceptance through VisaNet<br><br>Visa or Mastercard product ID that is associated with the primary account number (PAN).<br>For descriptions of the Visa product IDs, see the Product ID table on the [Visa<br>Request & Response Codes web page.](<br><br>Data Length: String (3)<br><br>#### GPN<br><br>Visa or Mastercard product ID that is associated with the primary account number (PAN).<br>For descriptions of the Visa product IDs, see the Product ID table on the<br>[Visa Request & Response Codes web page.](<br><br>Data Length: String (3)<br><br>#### Worldpay VAP<br><br>**Important** Before using this field on Worldpay VAP,<br>you must contact Visa Acceptance Customer Support to have<br>your account configured for this feature.<br><br>Type of card used in the transaction. The only possible value is:<br><br>- `PREPAID`: Prepaid Card<br><br>Data Length: String (7)<br><br>#### RBS WorldPay Atlanta<br><br>Type of card used in the transaction. Possible values:<br><br>- `B`: Business Card<br>- `O`: Noncommercial Card<br>- `R`: Corporate Card<br>- `S`: Purchase Card<br>- `Blank`: Purchase card not supported<br><br>Data Length: String (1)<br><br>**Constraints**: *Maximum Length*: `7` | getCategory(): ?string | setCategory(?string category): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountFeatures1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$accountFeatures1 = AccountFeatures1Builder::init()
    ->category('category4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

