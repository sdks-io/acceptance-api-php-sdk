
# Sender Information 1

*This model accepts additional fields of type array.*

## Structure

`SenderInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of the sender of the funds. For Gaming Payment of Winnings transactions these are the merchant details.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Must not be all numeric.<br>* Must contain only ASCII characters in range 32-122.<br>* Must not be greater than 35 characters including spaces.<br>* Required for POW on Barclays.<br><br>**Constraints**: *Maximum Length*: `35` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the sender of the funds. For Gaming Payment of Winnings transactions these are the merchant details.<br><br>* Optional for Mastercard Payment of Winnings (POW) transactions.<br>* Must not be all numeric.<br>* Must contain only ASCII characters in range 32-122.<br>* Must not be greater than 35 characters including spaces.<br>* Optional for POW on Barclays.<br><br>**Constraints**: *Maximum Length*: `35` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | Street address of the sender of the funds. For Gaming Payment of Winnings transactions these are the merchant details.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Must not be all numeric.<br>* Must contain only ASCII characters in range 32-122.<br>* Must not be greater than 50 characters including spaces.<br>* Required for POW on Barclays.<br><br>**Constraints**: *Maximum Length*: `50` | getAddress1(): ?string | setAddress1(?string address1): void |
| `locality` | `?string` | Optional | City of the sender of the funds. For Gaming Payment of Winnings transactions these are the merchant details.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Must not be all numeric.<br>* Must contain only ASCII characters in range 32-122.<br>* Must not be greater than 25 characters including spaces.<br>* Required for POW on Barclays.<br><br>**Constraints**: *Maximum Length*: `25` | getLocality(): ?string | setLocality(?string locality): void |
| `countryCode` | `?string` | Optional | Country of the sender of the funds. For Gaming Payment of Winnings transactions these are the merchant details.<br><br>* Required for Mastercard Payment of Winnings (POW) transactions.<br>* Must be a valid three character ISO country code as defined by ISO 3166.<br>* Must not be greater than 3 characters.<br>* Required for POW on Barclays.<br><br>**Constraints**: *Maximum Length*: `3` | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `account` | [`?Account6`](../../doc/models/account-6.md) | Optional | - | getAccount(): ?Account6 | setAccount(?Account6 account): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SenderInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$senderInformation1 = SenderInformation1Builder::init()
    ->firstName('firstName4')
    ->lastName('lastName2')
    ->address1('address16')
    ->locality('locality8')
    ->countryCode('countryCode4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

