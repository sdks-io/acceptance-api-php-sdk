
# Recipient Information 1

*This model accepts additional fields of type array.*

## Structure

`RecipientInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of recipient of the funds.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Must not be all numeric.<br>* Must contain only ASCII characters in range 32-122.<br>* Must not be greater than 35 characters including spaces.<br>* Required for POW on Barclays<br><br>**Constraints**: *Maximum Length*: `35` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of recipient of the funds.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Must not be all numeric.<br>* Must contain only ASCII characters in range 32-122.<br>* Must not be greater than 35 characters including spaces.<br>* Required for POW on Barclays<br><br>**Constraints**: *Maximum Length*: `35` | getLastName(): ?string | setLastName(?string lastName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RecipientInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$recipientInformation1 = RecipientInformation1Builder::init()
    ->firstName('firstName0')
    ->lastName('lastName8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

