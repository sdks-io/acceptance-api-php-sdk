
# Customer Account

*This model accepts additional fields of type array.*

## Structure

`CustomerAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `lastChangeDate` | `?string` | Optional | Date the cardholder’s account was last changed.<br>This includes changes to the billing or shipping address, new payment accounts or new users added.<br>Recommended for Discover ProtectBuy.<br><br>**Constraints**: *Maximum Length*: `10` | getLastChangeDate(): ?string | setLastChangeDate(?string lastChangeDate): void |
| `creationHistory` | `?string` | Optional | The values from the enum can be:<br><br>- GUEST<br>- NEW_ACCOUNT<br>- EXISTING_ACCOUNT | getCreationHistory(): ?string | setCreationHistory(?string creationHistory): void |
| `modificationHistory` | `?string` | Optional | This field is applicable only in case of EXISTING_ACCOUNT in creationHistory. Possible values:<br><br>- ACCOUNT_UPDATED_NOW<br>- ACCOUNT_UPDATED_PAST | getModificationHistory(): ?string | setModificationHistory(?string modificationHistory): void |
| `passwordHistory` | `?string` | Optional | This only applies for EXISTING_ACCOUNT in creationHistory.<br>The values from the enum can be:<br><br>- PASSWORD_CHANGED_NOW<br>- PASSWORD_CHANGED_PAST<br>- PASSWORD_NEVER_CHANGED | getPasswordHistory(): ?string | setPasswordHistory(?string passwordHistory): void |
| `createDate` | `?string` | Optional | Date the cardholder opened the account.<br>Recommended for Discover ProtectBuy.<br>This only applies for EXISTING_ACCOUNT in creationHistory.<br><br>**Constraints**: *Maximum Length*: `10` | getCreateDate(): ?string | setCreateDate(?string createDate): void |
| `passwordChangeDate` | `?string` | Optional | Date the cardholder last changed or reset password on account.<br>Recommended for Discover ProtectBuy.<br>This only applies for PASSWORD_CHANGED_PAST in passwordHistory.<br><br>**Constraints**: *Maximum Length*: `10` | getPasswordChangeDate(): ?string | setPasswordChangeDate(?string passwordChangeDate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerAccountBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$customerAccount = CustomerAccountBuilder::init()
    ->lastChangeDate('lastChangeDate8')
    ->creationHistory('creationHistory6')
    ->modificationHistory('modificationHistory0')
    ->passwordHistory('passwordHistory6')
    ->createDate('createDate2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

