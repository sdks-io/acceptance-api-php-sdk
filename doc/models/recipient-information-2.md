
# Recipient Information 2

*This model accepts additional fields of type array.*

## Structure

`RecipientInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountId` | `?string` | Optional | The account ID of the recipient. | getAccountId(): ?string | setAccountId(?string accountId): void |
| `createDate` | `?string` | Optional | The date when the recipient's account was created. | getCreateDate(): ?string | setCreateDate(?string createDate): void |
| `email` | `?string` | Optional | The email address of the recipient | getEmail(): ?string | setEmail(?string email): void |
| `countryCode` | `?string` | Optional | The country code of the recipient. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `businessName` | `?string` | Optional | The business name of the recipient. | getBusinessName(): ?string | setBusinessName(?string businessName): void |
| `riskPopularityScore` | `?string` | Optional | The risk popularity score of the recipient. | getRiskPopularityScore(): ?string | setRiskPopularityScore(?string riskPopularityScore): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RecipientInformation2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$recipientInformation2 = RecipientInformation2Builder::init()
    ->accountId('accountId4')
    ->createDate('createDate0')
    ->email('email2')
    ->countryCode('countryCode0')
    ->businessName('businessName2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

