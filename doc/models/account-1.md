
# Account 1

*This model accepts additional fields of type array.*

## Structure

`Account1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | The account number of the entity funding the transaction. The value for this field can be a payment card account number or bank account number.<br><br>**Constraints**: *Maximum Length*: `50` | getNumber(): ?string | setNumber(?string number): void |
| `type` | `?string` | Optional | Identifies the sender’s account type.<br>This field is applicable for AFT transactions.<br><br>Valid values are:<br><br>- `00` for Other<br>- `01` for Routing Transit Number (RTN) + Bank Account Number (BAN)<br>- `02` for International Bank Account Number (IBAN)<br>- `03` for Card Account<br>- `04` for Email<br>- `05` for Phone Number<br>- `06` for Bank Account Number (BAN) + Bank Identification Code (BIC), also known as a SWIFT code<br>- `07` for Wallet ID<br>- `08` for Social Network ID<br><br>**Constraints**: *Maximum Length*: `2` | getType(): ?string | setType(?string type): void |
| `fundsSource` | `?string` | Optional | Source of funds.<br>Possible Values:<br><br>- `01`: Credit.<br>- `02`: Debit.<br>- `03`: Prepaid.<br>- `04`: Deposit Account.<br>- `05`: Mobile Money Account.<br>- `06`: Cash.<br>- `07`: Other.<br>- `V5`: Debits / deposit access other than those linked to the cardholders’ scheme.<br>- `V6`: Credit accounts other than those linked to the cardholder’s scheme.<br><br>**Constraints**: *Maximum Length*: `2` | getFundsSource(): ?string | setFundsSource(?string fundsSource): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account1 = Account1Builder::init()
    ->number('number0')
    ->type('type8')
    ->fundsSource('fundsSource8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

