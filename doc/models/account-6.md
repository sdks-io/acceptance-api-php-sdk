
# Account 6

*This model accepts additional fields of type array.*

## Structure

`Account6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | Account number of the sender of the funds. For Gaming Payment of Winnings transactions this is the merchant account number.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Must contain only ASCII characters in range 32-122.<br>* Must not be greater than 50 characters.<br>* Required for POW on Barclays.<br><br>**Constraints**: *Maximum Length*: `50` | getNumber(): ?string | setNumber(?string number): void |
| `fundsSource` | `?string` | Optional | Source of funds for the sender. For Gaming Payment of Winnings transactions this is the merchant account type.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Valid values:<br>  * 00 - Other<br>  * 01 - RTN + Bank Account<br>  * 02 - IBAN<br>  * 03 - Card Account<br>  * 04 - Email<br>  * 05 - PhoneNumber<br>  * 06 - Bank account number (BAN) + Bank Identification Code (BIC)<br>  * 07 - Wallet ID<br>  * 08 - Social Network ID<br><br>**Constraints**: *Maximum Length*: `2` | getFundsSource(): ?string | setFundsSource(?string fundsSource): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account6 = Account6Builder::init()
    ->number('number4')
    ->fundsSource('fundsSource4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

