
# Card 13

The expirationMonth, expirationYear and securityCode is sent to the issuer as part of network token enrollment and is not stored under the Instrument Identifier.

*This model accepts additional fields of type array.*

## Structure

`Card13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | The customer’s payment card number, also known as the Primary Account Number (PAN). You can also use this field<br>for encoded account numbers.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `19` | getNumber(): ?string | setNumber(?string number): void |
| `expirationMonth` | `?string` | Optional | Two-digit month in which the payment card expires.<br><br>Format: `MM`.<br><br>Possible Values: `01` through `12`.<br><br>**Constraints**: *Maximum Length*: `2` | getExpirationMonth(): ?string | setExpirationMonth(?string expirationMonth): void |
| `expirationYear` | `?string` | Optional | Four-digit year in which the credit card expires.<br><br>Format: `YYYY`.<br><br>**Constraints**: *Maximum Length*: `4` | getExpirationYear(): ?string | setExpirationYear(?string expirationYear): void |
| `securityCode` | `?string` | Optional | Card Verification Code.<br>This value is sent to the issuer to support the approval of a network token provision.<br>It is not persisted against the Instrument Identifier.<br><br>**Constraints**: *Maximum Length*: `4` | getSecurityCode(): ?string | setSecurityCode(?string securityCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Card13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$card13 = Card13Builder::init()
    ->number('number6')
    ->expirationMonth('expirationMonth2')
    ->expirationYear('expirationYear2')
    ->securityCode('securityCode4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

