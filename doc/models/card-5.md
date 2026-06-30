
# Card 5

*This model accepts additional fields of type array.*

## Structure

`Card5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | The customer’s payment card number, also known as the Primary Account Number (PAN).<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `19` | getNumber(): ?string | setNumber(?string number): void |
| `expirationMonth` | `?string` | Optional | Two-digit month in which the payment card expires.<br><br>Format: `MM`.<br><br>Possible Values: `01` through `12`.<br><br>**Constraints**: *Maximum Length*: `2` | getExpirationMonth(): ?string | setExpirationMonth(?string expirationMonth): void |
| `expirationYear` | `?string` | Optional | Four-digit year in which the credit card expires.<br><br>Format: `YYYY`.<br><br>**Constraints**: *Maximum Length*: `4` | getExpirationYear(): ?string | setExpirationYear(?string expirationYear): void |
| `type` | `?string` | Optional | The type of card (Card Network).<br>Possible Values:<br><br>- 001: visa | getType(): ?string | setType(?string type): void |
| `suffix` | `?string` | Optional, Read-only | The customer’s latest payment card number suffix. | getSuffix(): ?string | setSuffix(?string suffix): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Card5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$card5 = Card5Builder::init()
    ->number('number8')
    ->expirationMonth('expirationMonth0')
    ->expirationYear('expirationYear4')
    ->type('type0')
    ->suffix('suffix0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

