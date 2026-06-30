
# Sender Information 2

*This model accepts additional fields of type array.*

## Structure

`SenderInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | [`?Account14`](../../doc/models/account-14.md) | Optional | - | getAccount(): ?Account14 | setAccount(?Account14 account): void |
| `firstName` | `?string` | Optional | The first name of the sender. | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | The last name of the sender. | getLastName(): ?string | setLastName(?string lastName): void |
| `email` | `?string` | Optional | The email address of the sender. | getEmail(): ?string | setEmail(?string email): void |
| `phoneNumber` | `?string` | Optional | The phone number of the sender. | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `countryCode` | `?string` | Optional | The country code of the sender. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `createDate` | `?string` | Optional | The date when the sender's account was created. | getCreateDate(): ?string | setCreateDate(?string createDate): void |
| `postalCode` | `?string` | Optional | The postal code of the sender. | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `riskPopularityScore` | `?string` | Optional | The risk popularity score of the sender. | getRiskPopularityScore(): ?string | setRiskPopularityScore(?string riskPopularityScore): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SenderInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account14Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$senderInformation2 = SenderInformation2Builder::init()
    ->account(
        Account14Builder::init()
            ->number('number8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->firstName('firstName0')
    ->lastName('lastName8')
    ->email('email2')
    ->phoneNumber('phoneNumber6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

